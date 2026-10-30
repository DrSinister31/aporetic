# AP-STAGE5-08 — Review sidebar hosts Computer View + Takeover in-view

| Field | Value |
|-------|-------|
| status | **INDEPENDENT PASS** — **not** Stage 5 complete |
| decision | Ali UX correction (authoritative): Conversation primary + collapsible Review right sidebar |
| branch | `stage4-an-shell` |
| worktree | `C:\Users\Dilla\.cursor\worktrees\opt\cursor-aporetic-stage4` |
| tip | `6e73823dc7` (docs head `16daf50e22`) |
| base | HEAD after STAGE5-07 docs tip `2ddf7b738f` / code `cf8c9ac361` |
| merge/push/install | **No** |

## UX correction vs Option C mode pills

| Before (STAGE5-01 Option C pills) | After (STAGE5-08) |
|-----------------------------------|-------------------|
| Peer mode pills: Conversation / Computer View / Takeover | No peer mode pills |
| Computer View swapped/widened attention or replaced stream in Takeover | Computer View lives in collapsible **Review** right sidebar |
| Takeover = peer mode; computer primary in main | Takeover = **in-view option** on Computer View in Review (Hand-back / Stop / Pause) |
| Conversation demoted during Takeover | Conversation **always** main stream |

Preserved: quiet entry, Status/Inline densities, scope+gold, Pause/named banners, CDP isolation, OS-pointer pause, EnginePort, Aporetic by Aporia Nous, BF Takeover honesty.

## What shipped

1. `AN_SHELL_UX` + layout flags `conversationPrimary` / `reviewHostsComputer` (computerBeside/Primary always false)
2. Mission chrome: Review toggle (not mode pills)
3. `AnLiveComputerPanel` hosted in `AnReviewPanel` Computer tab; Takeover dock inside Review
4. `session-layout`: view/takeover open Review; Hand-back stays watch-only in Review
5. Units + live CDP probe

## Evidence

| Shot | What |
|------|------|
| `145-stage5-08-conversation-primary-no-pills.png` | Conversation primary; no peer mode pills |
| `146-stage5-08-review-computer-sidebar.png` | Review open with Computer View |
| `147-stage5-08-review-computer-live.png` | Live Computer View in Review; Take over / Pause in-view |
| `148-stage5-08-takeover-in-review-dock.png` | Takeover Hand-back / Stop dock in Review |
| `149-stage5-08-handback-review-preserved.png` | Hand-back → watch-only Review; Conversation primary |

Independent live CDP: `cdp-probe-stage5-08-review-sidebar.mjs` → `ok:true` marker **`AP-STAGE5-08 review-sidebar 1792501979803`** EXIT=0 ws.closed

Writer prior marker (not independent): `1792501717903`

Board evidence: `business-control/evidence/2026-10-20-ap-stage5-08-independent-pass.txt`

## Tests

Independent re-run: `bun test src/shell/an` + `./src/aporia/flows-util.test.ts` from `packages/app` — **170 pass / 0 fail**

## Residuals

- Stage 5 Option C acceptance / Stage 5 complete still OPEN
- Native window capture remains BLOCKED; global OS hook UNSUPPORTED
- Casual Review iframe browser path only when Computer slot absent (session always hosts Computer)

## Not claimed

- Stage 5 complete
- Stage 5 Option C acceptance
- merge / push / promote
- new features
