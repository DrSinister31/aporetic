# Emergent implementation brief: Aporetic

Repository: https://github.com/DrSinister31/aporetic
Branch: dev
Read APORETIC-SNAPSHOT.md and AGENTS.md before working.

## Goal
Continue the existing Aporetic agentic desktop/web application toward a usable subscription product. Preserve the existing implementation and product identity. This is a Bun/TypeScript monorepo derived from OpenCode, with Electron in packages/desktop, web UI in packages/app, and agent execution in packages/core. Do not replace it with a newly scaffolded generic chatbot or dashboard.

## First deliverable
Inspect the actual source and report what works, what is incomplete, and what your environment can run. Map authentication, bot/team lanes, conversation state, shared memory, voice, computer/browser control, and billing surfaces. Treat historical implementation notes as claims requiring verification. Then implement the smallest coherent improvement on a separate branch and report changed files, checks, and remaining blockers. Keep dev as the review baseline.

## Product behavior
- Preserve bot/team lanes and the conversation-centered workspace.
- Keep user takeover, pause/resume, permissions, and visible control status intact.
- Use real backend state and persistence. Label unavailable integrations honestly; do not simulate successful execution or payment.
- Preserve Electron/local-host functionality. A browser preview does not prove Windows desktop or computer-control behavior. Document desktop checks that require Windows.
- Review existing UI and flows before changing design. Use plain English for customer-facing copy.

## Subscription implementation direction
Start in an isolated Stripe test environment. Do not create live charges, live plans, or change existing production billing.
Confirm which Stripe account is the seller: an owned platform/merchant account is different from a connected account controlled by another platform. Confirm whether Aporetic is part of the same operating business or an independent product/business before selecting an account. Keep existing products, customers, subscriptions, and webhooks untouched.
For fixed monthly/annual plans use Stripe Billing with Checkout and Customer Portal. Define a separate Product per tier and Prices for billing intervals; keep tier names, amounts, quotas, and trial policies configurable until approved. Connect is needed only for payment routing to other sellers/providers, not merely because this is SaaS.
Implement server-side customer-to-workspace mapping, verified webhook signatures, idempotent event processing, and server-enforced entitlements. Cover activation, renewal, failed payments, changes, cancellation, refunds, disputes, and fraud events with explicit policies. A success redirect is not proof of payment. Verify tenant isolation and duplicate/out-of-order event handling. Consider tax registrations and tax setup before collecting tax.
Do not promise unlimited paid model usage. First identify who pays model costs, whether users bring their own keys, and what limits and cost controls are appropriate.

## Secrets and scope
The public repository must remain free of credentials and personal data. Configure secrets only through the deployment secret store. Keep Stripe and model-provider secret keys out of browser bundles and distributed Electron code. Never embed the owner's shared Emergent model key into customer installations. Do not rotate keys unless the owner requests it. Do not access production conversations, databases, leads, or vaults.

## Acceptance evidence
Provide runnable setup commands verified against the repository, an honest browser preview if supported, focused tests for changed behavior, a list of desktop-only checks, and billing test results where billing is implemented. Do not report production readiness without end-to-end evidence. No live deployment or customer billing as part of this initial task.

