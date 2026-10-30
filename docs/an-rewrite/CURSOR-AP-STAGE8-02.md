# AP-STAGE8-02 — AnShell stream hotpath measured (non-design)

| Field | Value |
|-------|-------|
| status | **INDEPENDENT PASS** (source/unit stream hotpath — not Stage 8 complete) |
| branch | `stage4-an-shell` |
| worktree | `C:\Users\Dilla\.cursor\worktrees\opt\cursor-aporetic-stage4` |
| tip / code | `5bac458f62` |
| docs / HEAD | `ad68fbf74a` (code tip `5bac458f62` ancestor) |
| base | AP-STAGE8-01 tip `d53552a156` / HEAD prior `6df5c48589` |
| authority | Ali continue-finish 2026-10-21 (except design) |
| merge/push/install | **No** |

## Intent

Second Stage 8 non-design slice under Ali finish auth: measure AnShell Conversation stream projection hotpath (`buildContextCards` + `buildConversationStreamItems`) with coherent p50/p95 and pin Stage 5 quiet-entry (no idle wallpaper). **No** visual redesign, brand look changes, or Review/Computer freestyle. Visual fidelity vs mockups remains deferred.

## What shipped

| Piece | Path |
|-------|-------|
| `AN_PERF_SURFACE` + `measureStreamHotpath` + evaluate | `packages/app/src/shell/an/perf-contract.ts` |
| Units | `packages/app/src/shell/an/perf-contract.test.ts` |
| Metrics | `business-control/evidence/2026-10-21-ap-stage8-02-metrics.json` |

## Checks (P1–P4)

| id | bar | result |
|----|-----|--------|
| P1 | stream hotpath measured (msgs/iters + finite p50≤p95) | **PASS** (independent) |
| P2 | quiet-entry: idle 0 computer/team wallpaper; mission stack empty | **PASS** (independent) |
| P3 | projection scale: turns=msgs; quiet reads not surfaced | **PASS** (independent) |
| P4 | noVisualRedesign scope pin | **PASS** (independent) |

## Independent remasure (fixture)

- msgs=80 iters=24
- p50Ms≈0.041 p95Ms≈0.062 (soft budget p95 &lt; 250ms — coherence; writer claimed ≈0.040/0.051 — same band)
- turns=80 items=91 cards=11; idleWallpaperCardCount=0; quietReadCardsSurfaced=0
- Honesty: baseline/coherence — **not** wall-clock win vs prior baseline; **not** live CDP paint

## Independent verification

- perf-contract → **5 pass**
- a11y-contract → **6 pass** (STAGE8-01 non-regress)
- shell/an + flows-util → **190 pass**
- Stage 7 isolation-attach non-regress → **6 pass**
- tokens → **26 pass**
- Diff `5bac458f62`: perf-contract + exports + docs only — no `*.css` / `*.tsx` redesign

## Residuals OK

- Stage 8 overall not complete (parent `AP-STAGE8` remains OPEN)
- Visual fidelity / side-by-side mockup audit — deferred (Ali design-except)
- Live CDP paint / FPS not claimed
- Engine E26 harness remains separate
- Stage 9 not started

## Not claimed

- Stage 8 complete / visual PASS
- Wall-clock win vs baseline
- Live CDP perf audit
- Merge / push / install
- UI redesign
