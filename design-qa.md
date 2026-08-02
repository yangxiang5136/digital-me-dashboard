# Digital Me architecture baseline — design QA

## Reference

- Live baseline: `https://digital-me-dashboard.vercel.app/`
- Every state below was reviewed against screenshots captured at 1440×810 for desktop and
  390×844 for mobile. Those captures, and the side-by-side comparison scaffold built from
  them, stay in the local `qa/` working directory: this repository is the public Vercel
  deploy root, so QA evidence is never committed or deployed. This file is the committed
  record of what the captures showed.

## Visual comparison

- Preserved the live site's typography, spacing, blue gradient, card language, and diagram treatment. The top bar was later re-aligned with the personal Portfolio — see the navigation alignment section below.
- Removed the runtime-status banner and promoted the architecture entry point to the first featured card and first section.
- Reduced the public topology to six stable roles with no live-state, cadence, retired-pipeline, or experimental-branch details.
- Kept the agent cross-section and human decision gate while removing the four implementation-detail cards.
- Replaced the long philosophy gallery with one compact closing statement and three principles.

## Functional and responsive checks

- Navigation, language switching, and back-to-top behavior are recorded in the navigation alignment section below.
- The GitHub control is explicitly labeled as a profile link and opens the verified public profile.
- Desktop and mobile states have no document-level horizontal overflow.
- On mobile, the section pills collapse out of the top bar, leaving the identity line, the icon-only GitHub control, and the language toggle, and the architecture diagram remains visible as the first project artifact.
- The architecture diagram was checked in both languages on mobile and desktop: every tier label clears its nearest connector, with the longest label (`UNDERSTAND`) ending at x=123.1 against the connector at x=128.
- All three diagram accessible names (data flow, agent cross-section, human gate) describe the nodes currently drawn.

## Portfolio navigation alignment — 2026-08-02

- Visual source of truth: the author's personal Portfolio site, reviewed from a local
  working copy that is not part of this repository.
- Desktop, mobile, and scrolled Chinese states of the new top bar were captured before and
  after the change and compared side by side against the Portfolio source.
- Matched the Portfolio's fixed translucent bar, quiet identity line, pill navigation, two-state language control, active-section feedback, and labelled back-to-top action.
- Preserved Digital Me's own violet-blue identity and architecture-first page hierarchy instead of importing the Portfolio's ambient background or project-page content styling.
- Every top-bar control keeps a minimum 44×44 px target. The full segmented section navigation remains visible at 760 px and above, then collapses below that Portfolio-aligned breakpoint.
- Anchor navigation now jumps directly instead of smooth-scrolling. Architecture, Agents, Guardrails, and Why all resolve to existing sections and update the active pill.
- The active pill is exposed as `aria-current`, is recomputed on scroll, resize, and language switch, and the last pill stays active once the page is scrolled to the bottom.
- Chinese / English switching updates page content, document language, navigation labels, button labels, and accessibility names. The selected language remains explicit through `aria-pressed`.
- Section 03 keeps the concise `Guardrails / 约束` navigation label while its eyebrow switches between `03 · Harness engineering` and `03 · 运行边界`.
- Back-to-top becomes keyboard reachable only while visible, returns to `scrollY = 0`, then leaves the tab order.
- Checked at the in-app browser's desktop viewport and a requested 390 × 844 mobile viewport. Neither state has document-level horizontal overflow.

final result: passed
