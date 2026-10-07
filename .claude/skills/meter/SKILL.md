---
name: meter
description: Read this session's meter -- the account's 5-hour limit status and when it resets, this session's context used, and its cost so far. Reach for it on "where are we on tokens", "am I near the limit", "when does it reset", "what has this cost". No argument.
---
Purpose: a current reading, from the one session that can give one.

Procedure:

1. Call `get_session` from the claude-code-remote MCP tools with no
   session_id; it then describes this session. If the tool is
   deferred, load it first with ToolSearch,
   `select:mcp__claude-code-remote__get_session`.

2. From `external_metadata` take:
   - `rate_limit_info`: `status`, `rateLimitType`, `resetsAt` (epoch
     seconds), `isUsingOverage`
   - `context_usage`: `used_tokens` of `max_tokens`
   - `usage`: `cost_usd`

3. Turn the reset into a time and a countdown:

       date -u -d @RESETSAT '+%H:%M UTC %a %b %d'
       echo $(( (RESETSAT - $(date +%s)) / 60 )) minutes

4. Report one short block: the limit's type and status, when it resets
   and how long until then, whether overage is in use, context used of
   max with its percentage, and cost.

Facts:

- `status` is a label, such as `allowed` or `allowed_warning`, not a
  percentage. Nothing here says how much of the window is left: say
  the label, and do not guess a number.
- The limit is the account's, shared by every session on it. The
  context and cost are this session's.
- This reading is current because this session is the one asking.
  Another session's reading is from its own last turn; `meter-all`
  marks those stale once their window has reset.
</content>
