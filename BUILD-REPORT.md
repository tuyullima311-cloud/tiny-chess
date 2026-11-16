# Build report — tiny-chess-01

**Artifact**: `main.py`, **4,009 bytes** (cap 4,096), sha256
`2bd6e345…2f5`, built by `node cli/makefun.mjs compress
expA_min.py`. Source `expA_min.py` (14,475 B;
comment-stripped `expA.py`) is in
`~/workspace/makefun/work/chess-src/`.

**Design**: 0x88 board, incremental Zobrist key, tapered eval
(material + 7 PSTs incl. real queen table and king endgame
delta); alpha-beta + PVS, TT, null-move pruning, LMR, check
extensions, in-search repetition draws; quiescence
(captures, promotions, evasions). Fixed 50,000 nodes/move,
no clock.

**Practice results** (kit env + scorer; 6 games/trial vs
anchors 855…1596; baseline 1364/1451/1279, mean 1365;
floor 1154):
- **This entry: 1451 / 1451 / 1191 → mean 1364** (t0 3W/2D/1L
  incl. wins vs nodes-250k/500k; t1 4W/0D/2L; t2 2W/1D/3L).
  Level with the baseline's mean — a real contender, not a
  lock; the final uses fresh openings, 8-game sets.
- engine10 (4,042 B): 1191 trial-0. expC: 1099 (packing
  4,251 B, over cap). This engine at 100k nodes: 1099
  trial-0 — worse paired, so 50k ships.

**Verification**: perft 19/19 exact. Determinism: trial-0
run 3×, state.json sha256 identical (`2a3d4e35…deb`),
transcripts byte-identical. Legality: 30 gauntlet games,
zero illegal moves/crashes/resignations/time losses;
entry's 18 games, 0 abnormal endings. Think (env): mean
≈1.0 s/move, max 1.7 s (cap 10 s). Stdlib only, no model
calls; only /game /move /resign + prompt.txt.

**Left to submit**: public GitHub repo (once the account
appeal resolves) pushed unchanged; README badges + About
finished with the real `<owner>/<repo>`; `makefun bundle`
+ `check`; submit unsigned before 25 Nov 2026 00:00 WIB.
