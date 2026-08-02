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
- Every top-bar control keeps a minimum 44×44 px target, verified by measuring the section
  pills, the GitHub control, and both language buttons across the 320–1440 px range rather
  than at the two capture widths alone. The GitHub control is sized with `min-width` and is
  not shrinkable, so it holds 44×44 px even in the narrow desktop band where the bar is
  tightest. The full segmented section navigation remains visible at 760 px and above, then
  collapses below that Portfolio-aligned breakpoint.
- Below roughly 790 px the descriptive half of the identity line (`· Personal AI Architecture`
  / `· 个人 AI 架构`) is hidden while the `Digital Me` name stays visible. That frees the width
  the full pill navigation needs between 760 px and 790 px, so the bar stays within its own
  horizontal padding instead of running over capacity.
- The fixed bar's height and the body's top offset are both driven by the shared
  `--topbar-h` custom property (69 px), so the two cannot drift apart.
- Anchor navigation now jumps directly instead of smooth-scrolling. Architecture, Agents, Guardrails, and Why all resolve to existing sections and update the active pill.
- The active pill is exposed as `aria-current`, is recomputed on scroll, resize, and language switch, and the last pill stays active once the page is scrolled to the bottom.
- Chinese / English switching updates page content, document language, navigation labels, button labels, and accessibility names. The selected language remains explicit through `aria-pressed`.
- Section 03 keeps the concise `Guardrails / 约束` navigation label while its eyebrow switches between `03 · Harness engineering` and `03 · 运行边界`.
- Back-to-top becomes keyboard reachable only while visible, returns to `scrollY = 0`, then leaves the tab order. Activating it moves focus to the identity link at the top of the page before the button is hidden, so keyboard focus is never left on a hidden, `aria-hidden` element.
- Checked at the in-app browser's desktop viewport, the 760–790 px narrow desktop band, and a requested 390 × 844 mobile viewport. No state has document-level horizontal overflow.

final result: passed
