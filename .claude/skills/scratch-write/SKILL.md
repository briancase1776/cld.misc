---
name: scratch-write
description: Capture the current input into a scratch pad, organized, committed, pushed. Fire it UNPROMPTED whenever Brian jots or rambles ideas and a pad is open (fare mode) -- at each natural pause, do not wait for a capture phrase. Also on explicit asks ("get this down", "pad that", "capture this before i lose it") and multi-item dumps (session pad, capture-first, so no thread drops). Takes a topic name, or "session" for the session pad; with no argument, infers the pad from context and confirms inline.
---
Purpose: the write side of the pads -- Brian's scattered input becomes
organized distillate NOW, while it is still in front of us, so nothing
rides on the session surviving. Substrate: Claude/scratch/ per the
format spec. This is also how a Sonnet rambling session ships its
distillate back: write the pad, push, done -- the next session reads
it cold.

Procedure:

1. Read Claude/scratch-pad-format.txt FIRST -- this skill PRODUCES
   the format, so it cites the spec, never paraphrases it.

2. Resolve the target pad from $ARGUMENTS (or infer from what is
   being captured; confirm the inference inline in one line). "session"
   -> Claude/scratch/session.md; anything else -> the topic pad.
   Creating a new pad: use the topic-pad skeleton from the spec, add
   its line to Claude/scratch/index.cld (same commit), and if it
   serves a plan item, tell Brian the edge may want wiring
   (/plan-write-back, separate weld).

3. DISTILL, then write, per the spec's sections:
   - each point dated + attributed, in as close to Brian's words as
     survives distillation -- append to Points
   - questions he left hanging -> Open questions
   - a position clashing with a captured one -> Contradictions; keep
     BOTH, never silently reconcile
   - REWRITE "Where the thread is" so the next reader boots true
   - session pad: skip the ceremony, dated bullets are enough --
     capture verbatim-ish FIRST, work the threads after.

4. PREVIEW: show Brian the distilled delta -- the new points, moved
   questions, rewritten thread line -- inline, BEFORE committing, and
   wait for his ok (spec rule: no pad write lands unpreviewed).
   Corrections happen now, while the raw exchange is still in
   context; this is the loss-control for lossy distillation. Session
   pad excepted -- it is verbatim-ish capture, nothing distilled away
   yet; its preview happens at the /wrap drain.

5. Writing to a DRAINED pad is a failure -- report it, do not write;
   the topic graduated and new thinking goes to its spec or a fresh
   pad (Brian's call, asked inline).

6. If the pad serves a plan item (its OPENED line or a needs edge
   says so), leave the dated freshness one-liner on that item's body
   .md per the spec's rule -- replace the previous freshness line,
   same commit as the pad write. A pad serving no item skips this.

7. Commit (pad + index.cld + any freshness line together) and PUSH --
   an unpushed pad is invisible to the session that needs it (the
   spec's welded rule). Push failure is reported loudly, never
   swallowed.

Scope guard: writes Claude/scratch/ (pads + its index.cld) plus, for
a pad serving a plan item, ONLY the dated freshness one-liner on that
item's body .md -- never its bucket.json, edges, or status. All other
plan edits are /plan-write-back; graduation is /scratch-drain.
