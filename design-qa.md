# Digital Me architecture baseline — design QA

## Reference

- Live baseline: `https://digital-me-dashboard.vercel.app/`
- Side-by-side evidence: `qa/source-vs-minimal.jpg` (live baseline on the left, minimal architecture-first revision on the right)
- Final desktop states: `qa/minimal-desktop-en-final.jpg`, `qa/minimal-desktop-zh.jpg`
- Final mobile states: `qa/minimal-mobile-hero-zh-final.jpg`, `qa/minimal-mobile-structure-zh-final.jpg`, `qa/minimal-mobile-structure-en-final.jpg`
- Every screenshot above was captured from the current revision of `index.html`, at 1440x810 for desktop and 390x844 for mobile.

## Visual comparison

- Preserved the live site's typography, spacing, blue gradient, card language, sticky navigation, and diagram treatment.
- Removed the runtime-status banner and promoted the architecture entry point to the first featured card and first section.
- Reduced the public topology to six stable roles with no live-state, cadence, retired-pipeline, or experimental-branch details.
- Kept the agent cross-section and human decision gate while removing the four implementation-detail cards.
- Replaced the long philosophy gallery with one compact closing statement and three principles.

## Functional and responsive checks

- Internal navigation resolves to four existing section anchors in the same order as the page.
- The GitHub control is explicitly labeled as a profile link and opens the verified public profile.
- Chinese and English switching updates content, document language, and title.
- The back-to-top control remains available after scrolling.
- Desktop and mobile states have no document-level horizontal overflow.
- On mobile, the GitHub label collapses to its source icon in a 44x44 tap target matching the language button, and the architecture diagram remains visible as the first project artifact.
- The architecture diagram was checked in both languages on mobile and desktop: every tier label clears its nearest connector, with the longest label (`UNDERSTAND`) ending at x=123.1 against the connector at x=128.
- Both diagram accessible names describe the nodes currently drawn.

Result: passed
