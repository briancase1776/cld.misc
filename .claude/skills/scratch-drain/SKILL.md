---
name: scratch-drain
description: Graduate a topic pad into its real home -- a type:ramblings node holding Brian's own description sorted, a notes/*.md spec draft, and/or plan items -- and mark the pad drained. Reach for it on "bring it back", "drain the pad", "turn the <topic> pad into the spec", or when a pad's open questions are all ruled and the thinking has settled. Takes the topic name; with no argument, prints usage plus any pads that look ready to drain.
---
Purpose: the bring-it-back half of Brian's flow ("let sonnet deal
with my ramblings, then bring it back"). A pad is a waypoint, not a
home -- when the thinking settles, its payload becomes a durable spec
or plan items, and the pad stops accepting writes. Substrate:
Claude/scratch/ per Claude/scratch-pad-format.txt (cited, not
paraphrased -- this skill writes the STATUS line and the destination
files).

Procedure:

1. NO ARGUMENT: print one-line usage, then list open pads whose Open
   questions section is empty or fully ruled -- the drain candidates.
   Draining is Brian's call; suggest, do not start.

2. Read the pad fully. A drain with UNRULED open questions or live
   contradictions is premature: list them and stop -- those are
   Brian's rulings, taken inline, before any drain.

3. Draft the destination WITH Brian. A pad drains into up to THREE
   places, and the first one is the one this skill spent months
   without:

   a. A type:ramblings NODE for Brian's own description of the thing.
      His words, SORTED -- order added and nothing else: nothing
      thrown away, nothing decided, nothing refined. This is the
      destination the skill lacked, and its absence is why pads do
      not drain: every other artifact on a pad had a home (rulings
      became items, design became a spec) and his description had
      none, so a drain that would drop it is a drain nobody runs.
      Never fold his description into the spec instead -- the spec is
      DERIVED from it and it must outlive the build ("4 years after
      layers is built you can actually read what i said when i
      described it"). See plan-tree.md "ramblings -- the one type
      with no terminus".
   b. A notes/<topic>.md spec, the distil and refinement (dev-
      practices hygiene; it is a real doc now, not a pad). This is
      the one that throws things away, which is exactly why it cannot
      also be (a).
   c. Plan items for the work that falls out.

   The pad's Points are the raw material. The (b) draft is presented
   for his read BEFORE committing -- it is the one output claiming to
   be settled thinking, so he confirms it. (a) needs no such
   confirmation: it asserts nothing, it only orders what he said.

4. Plan changes fall out (the type:ramblings node from 3a, new
   items, edges, statuses -- e.g. a needs edge onto the item the pad
   served): route ALL of them through /plan-write-back with its own
   weld; this skill does not hand-edit the plan tree.

5. Seal the pad: STATUS "drained -> <destination(s)>, YYYY-MM-DD",
   update its index.cld gist to say drained (same commit), leave
   everything else in place as history. Commit and PUSH (pad weld
   rule); the spec/notes files ride the same commit unless Brian
   wants them separate.

Scope guard: writes Claude/scratch/ (STATUS + index.cld) and the NEW
destination files Brian approved (notes/*.md). Plan tree edits go
through /plan-write-back, never directly from here.
