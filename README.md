# cld.misc

Small Claude Code skills that belong to no bigger kit. Kept simple: a
skill is a SKILL.md, and does one thing.

    meter       this session's limit status and reset, context, cost
    meter-all   every recent session's context, cost and last limit
                reading, stale ones marked
    scratch, scratch-write, scratch-drain
                the scratch-pad kit: open a pad, capture into it,
                graduate it

Both read session records through the claude-code-remote MCP tools,
which only cloud sessions have, and never wake a session.
meter-all needs jq.

The scratch kit moved here from DNATools on 2026-10-21, unchanged. It
still works on the repo in front of it the DNATools way: pads in
Claude/scratch/, the format in Claude/scratch-pad-format.txt, plan
changes through /plan-write-back. Nothing arms it any more; reach for
it by name.

## Licence

MIT. See LICENCE.TXT.
