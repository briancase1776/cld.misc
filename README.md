# cld.misc

Small Claude Code skills that belong to no bigger kit. Kept simple: a
skill is a SKILL.md, and does one thing.

    meter       this session's limit status and reset, context, cost
    meter-all   every recent session's context, cost and last limit
                reading, stale ones marked
    me          IRC-style /me: shows Brian's action and carries on

meter and meter-all read session records through the claude-code-remote
MCP tools, which only cloud sessions have, and never wake a session.
meter-all needs jq.

## Licence

MIT. See LICENCE.TXT.
