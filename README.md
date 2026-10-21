# cld.misc

Small Claude Code skills that belong to no bigger kit. Kept simple: a
skill is a SKILL.md, and does one thing.

    meter       this session's limit status and reset, context, cost
    meter-all   every recent session's context, cost and last limit
                reading, stale ones marked
    scratch, scratch-write, scratch-drain
                the scratch-pad kit: open a pad, capture into it,
                graduate it
    fanout-writers
                N writer-subagents argue a design, one builds it,
                the session commits

Both read session records through the claude-code-remote MCP tools,
which only cloud sessions have, and never wake a session.
meter-all needs jq.

The scratch kit and fanout-writers moved here from DNATools on
2026-10-21, unchanged, to be developed here. They still work on the
repo in front of them the DNATools way: pads and the ICC maildir in
Claude/scratch/, the pad format in Claude/scratch-pad-format.txt,
plan changes through /plan-write-back. DNATools' SessionStart hook
still runs /scratch there, so a DNATools session needs this repo
attached.

## Licence

MIT. See LICENCE.TXT.
