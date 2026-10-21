---
name: scratch
description: Open a scratch pad, report where the thread left off, and ARM the session (fare mode) -- from then on Brian's ideas are captured to the pad at every natural pause, unprompted. Reach for it on "open the layers pad", "where were we on <topic>", "pick up the <topic> thread", or FIRST THING in any talk-it-out / rambling session (Sonnet sessions especially): open the pad BEFORE the rambling starts. Takes a topic name; with no argument, lists every pad and its status.
---
Purpose: boot a cross-session (cross-model) conversation from its pad
instead of from memory nobody has. The pads live in Claude/scratch/
(session.md + one <topic>.md per topic); the pad's "Where the thread
is" section is the boot loader. This is the read side -- capturing new
input is /scratch-write, graduating the pad is /scratch-drain.

Procedure:

1. NO ARGUMENT: list the pads -- read Claude/scratch/index.cld and
   each pad's STATUS line. Report one line per pad: name, open/
   drained, and its "Where the thread is" first line. Mention
   session.md only if it exists (it exists only when captures are
   pending).

2. TOPIC given (exact pad name or a paraphrase -- match against pad
   filenames and index.cld gists; ambiguity is resolved inline in
   plain text, never the AskUserQuestion popup):
   - Pad exists: read it fully. Report: STATUS, "Where the thread is"
     verbatim, the open questions, any contradictions awaiting ruling.
     Then let Brian talk -- the pad boots the thread, it does not
     replace it -- but the session is now ARMED (fare mode, per the
     spec): from here until wrap, Brian's substantive input IS pad
     input. At each natural pause (his "ok", a topic shift, a lull),
     run the /scratch-write procedure for this pad -- distill,
     preview, commit, push -- WITHOUT waiting to be asked. Do not let
     ramblings scroll by uncaptured; that is the leak this mode
     exists to kill.
   - Pad is drained: say so and point at where it graduated (the
     STATUS line carries the pointer). Do not reopen without Brian
     saying to.
   - No such pad: offer to open one -- a new pad is a WRITE, so hand
     off to /scratch-write (which creates it per the format spec)
     rather than creating it here.

3. If the pad references sessions or models still expected to write
   (e.g. a Sonnet session in flight), `git pull` first so the report
   reflects origin, not a stale clone.

Scope guard: READ-ONLY in itself -- this skill prints; it never edits
a pad, never creates one, never changes STATUS. The fare mode it arms
does its writing through /scratch-write's procedure and scope, not
this skill's.
