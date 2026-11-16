# Build transcript summary — tiny-chess-01

Two Muse sessions, 16 Nov 2026; full transcripts bundled
at submission.

S1 (earlier agent): engine.py → engine2..10 (20.6→14.2 KB),
each packed with `makefun compress` (packed10 4,042 B, the
only early one under the cap); forked expA/expC from
engine9; stopped with no results recorded.

S2 (finishing agent): read RULES.txt; local rig (kit env
server + scorer). Trial-0: expA 1451, engine10 1191, expC
1099; expA/XC packings were 4,238/4,251 B, over the cap →
stripped expA's comments → expA_min.py → compress →
**4,009 B** (identity proven: bench, perft, byte-identical
trial-0 state). Trials 1–2: 1451, 1191 → mean 1364
(baseline 1365, floor 1154). BUD 100k rejected (trial-0
1099). Packaged here; no login/submit done.
