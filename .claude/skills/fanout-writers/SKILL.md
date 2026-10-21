---
name: fanout-writers
description: Design-argue-build one plan item with N parallel subagent WRITERS consulting over the ICC maildir -- independent positions, adversarial rounds, a designated spec-writer, ONE builder, cross-review, the session as clock and sole pen. Reach for it on "spawn N opuses/claudes and have them work it out together", "consult each other and build it", "fan out writers" -- for multi-subsystem items where cross-examination pays. NOT /fanout (that fan is read-only sweep+synthesize; its scope guard forbids writers). Never launches without stating width, model tier, and cost, and never without Brian's explicit go. The METHOD lives in Claude/scratch/icc-fan.md; step 0 requires reading it BEFORE briefing any writer -- these steps are the compression, the pad is where the value comes from.
---
Purpose: one careful session misses what three argued positions catch.
Multi-subsystem items only; a one-file feature does not pay.

Cost, stated to Brian BEFORE launching, every time:

NOT RECOMMENDED ON LESS THAN MAX. This is the most expensive shape in
the project and it is not a close call.

Quote what can actually be counted -- width, model tier, and the
measured cost of comparable runs: ~2.2M subagent tokens at width 3 for
a 2000-line code feature (2026-08-05), ~350k at width 3 for a 156-line
skill (2026-08-11). Do NOT quote a formula: the session cannot see the
account, the plan, or what is left of the week, so it cannot price the
run in the unit Brian actually spends. Say that out loud rather than
implying the number means more than it does.

Default width 3, the session model or better for every writer -- no
cheap-tier writers, judgment is the whole point. Brian's explicit go
required, no exceptions. Auditing something already built is a thinner
job than design-before-build; say which one you are quoting.

Topology: star for TRIGGERS, mesh for CONTENT. Subagents cannot wake
each other; the session is the clock. Content flows peer-to-peer
through Claude/scratch/icc/<sessionid>-<letter>.md, filesystem
transport. ICC protocol holds: own file ONLY, append-only, stamp
who/when/commit, end with ASK, never touch the README or another's
file.

Procedure:

0. READ Claude/scratch/icc-fan.md BEFORE YOU WRITE A SINGLE BRIEF.
   Not after, not "if unsure". These steps are the compression; the
   pad is the method, and it holds the two killed rounds, the pen,
   and why each rule below exists. Briefing harder looks like doing
   it better and is the one thing that kills the mechanism.

1. SCOPE inline, FOR YOURSELF: read the item body and enough code
   (via the .cld indexes) to judge whether the item is worth the fan.
   Decide WIDTH. Quote width+model+cost; wait for Brian's go. What
   you learn here is for that judgment, NOT a work breakdown to hand
   out.

2. ROUND 1 -- positions. Each writer boots COLD. The brief is
   BYTE-IDENTICAL for every writer except its outbox filename.
   The brief carries the JOB and the RAILS, nothing else:
   - the job in one line, then: how you go about it is entirely yours
   - the item body path (the job, not a reading list)
   - the way in: CLAUDE.md and the .cld indexes. Which files matter
     is the writer's call.
   - the ICC protocol digest and its own outbox path
   - read-only git only: log, show, diff, rev-parse. No commit, add,
     push, branch, checkout. The session commits.
   - APPEND TO THE OUTBOX AS YOU FIND, never one write at the end
   - development-practices pointer
   - the return shape (5-10 lines; content lives in the outbox)
   - the lock path IF the round shares an output file (step 6)
   NOT in the brief: a lens, a reading order, a file list, or the
   session's theory of the item. Parallel, one message.
   COMPOSE IT ONCE, INTO A FILE, and send that file's bytes to every
   writer -- scratch dir, not the repo. Byte-identical is the
   mechanism, and typing it N times is how it stops being true. Only
   the outbox line differs; substitute it per writer at send time.

3. ROUND 2 -- cross-read. Each reads the others' outboxes, answers
   the ASKs aimed at it, states dissents WITH file:line evidence
   ("disagreement is wanted; do not average"). EXPECT CROSSED MAIL:
   concurrent writers answer round-1 positions, not each other's
   round 2 -- plan for it, do not fight it.

4. ROUND 3 -- consolidate. Appoint ONE spec-writer (whoever won the
   arguments on evidence, not rotation) to read everything, rule the
   dangling dissents, and write the FINAL SPEC: numbered,
   file-by-file, symbols named, an explicit OUT list, and a Third
   Rock hand-off list (what will look broken and is not). Another
   all-hands round is the expensive way to converge; do not.

5. ACK ROUND -- the other writers verify the spec, with two duties
   each, and an unverified "looks fine" is worse than an objection:
   - AGAINST CODE: the claims touching the ground it argued in
     rounds 1-2. Duties are named from what a writer actually did,
     never assigned ahead of it.
   - AGAINST THE RUN'S OWN OPEN QUESTIONS: one RECONCILIATION LIST --
     every question raised in rounds 1-2 and where it landed (in the
     spec, filed as a node, or standing for Brian). A question that
     appears nowhere is a BLOCKER, and so is a spec sentence that
     ANSWERS an open question in passing without saying so. This is
     step 10's filed-with-homes rule, one stage earlier, pointed at
     questions.
   Both duties sit with the NON-spec-writers. Blockers loop to the
   spec-writer; acks proceed.

6. BUILD -- ONE writer at a time on any shared file, but THEY settle
   who and when (see "The pen"); the session names the lock path and
   stops there. READ-ONLY GIT ONLY -- log, show, diff, rev-parse; no
   commit, add, push, branch, checkout. The tree stays dirty and the
   session commits. Deviations from the spec are legal but every one
   goes in the build report -- the failure class to hunt later is the
   unlisted deviation.

7. REVIEW ROUND -- the non-builders review the RAW DIFF against the
   acked spec: the same self-named duties as step 5, plus
   hunt-the-unlisted-deviation. Verdict: APPROVE or numbered blockers
   with file:line; nits labeled nits.

8. FIX ROUND -- builder fixes blockers, triages nits (a declined nit
   states why and gets a recorded home). Any behaviour change no
   reviewer acked is flagged as an ASK for the last review to rule.

9. LAST REVIEW -- the session itself, always. Read the diff with own
   eyes, RE-RUN the tests personally, run compliance, and apply two
   lenses:
   - COLD REPRODUCIBILITY: can a fresh session reproduce every claim
     from the repo alone? (Scratch-space test drivers land in tests/.)
   - FIND FIRST: on every new node the run files, does any clause
     already have an owning plan item? plan-dupecheck guards ids
     only; the concept namespace needs a /plan-find per clause.
   Rule the flagged ASKs.

10. ONE PEN: the session commits everything -- outbox mail as it
    lands (the argued record is a deliverable), the reviewed code,
    the plan write-back (item DONE, new bugs filed with homes), and
    the Third Rock hand-off goes to Brian BEFORE he live-verifies.
    FILED WITH HOMES MEANS ALL OF IT: every hand-off and OUT-list
    entry gets a filed node or an explicit no-home ruling recorded
    beside it, and a walked-past CATEGORY need (keyboard, a11y,
    save, ...) is LISTED on its owning item, dated with provenance,
    never bundled into a one-off node. An unfiled hand-off entry
    evaporates.

Standing rule: a user line arriving in the same delivery as agent
traffic is captured to the session pad BEFORE any agent business is
touched. The notification is loud, Brian's line is quiet, and the fan
makes the interleave constant.

ROLL CALL, ON EVERY WAKE -- a writer finishing, or Brian saying
anything. Two questions, two instruments: LIST THE AGENTS (alive?) and
STAT THE OUTBOXES (moved?). Neither alone tells you anything -- a hung
writer is alive and flat, a dead one is gone and flat. Say out loud
which did not move.

Missing or flat: TOSS IN A SUB, no deliberation. Same brief block,
plus the outbox it is taking over -- append-as-you-find already put
that writer's position on disk, so a sub inherits it instead of paying
to re-derive it. No timeout and no abort clause anywhere in this file:
Brian is the interrupt, and the run costs nothing while it waits.

## The pen -- when N writers share one output file

Coordination is THEIRS. The session's only move: if writers will share
an output file, NAME THE CLAIM PATH IN THE BRIEF -- one line, "if you
take the pen, claim it at <path>" -- or assign the pen up front. That
is a rail; it says where the lock lives, never who wins. Do not
choreograph the merge.

A lock invented mid-run cannot be discovered by peers who are already
writing, and this channel forbids polling -- which is why the path
goes in the brief, before anyone starts. The 08-10 run's pen, its
protocol, and the inspection of why it failed are in icc-fan.md.

## Do not assign

THE SESSION'S JOB IS THE JOB, THE RAILS, AND THE COMMITS. Nothing
else.

- Do not assign lenses. Where the work has natural sides the writers
  find them; where it has none, handing out three manufactures the
  diversity instead of letting it arise.
- Do not assign reading paths. What they read, in what order, and
  what they judge worth attacking IS the finding.
- Do not impose coordination. See the pen.
- Do not hand a writer the session's own theory. It stops being an
  independent reading the moment you do.

The brief that worked was byte-identical for all three writers except
the outbox filename, and said the job, then said how you go about that
is entirely yours.

Scope guard: the session holds every COMMIT, every plan edit, and the
last review; writers run READ-ONLY GIT ONLY -- log, show, diff,
rev-parse; no commit, add, push, branch, checkout. Who writes the shared
output file, and when, is THEIRS. Never nests (a writer does not fan).
Never launches on the session's own initiative -- Brian's go, every
time.
