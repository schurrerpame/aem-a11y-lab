# AEM Accessibility Lab

Accessible blocks for **Adobe Experience Manager – Edge Delivery Services**, designed and validated against **WCAG 2.2 AA** and **EN 301 549**.

- **Live site:** https://main--aem-a11y-lab--schurrerpame.aem.live/
- **Status:** work in progress (started October 2026). Blocks are added as they pass validation.

## Why this lab

Most accessibility issues on enterprise CMS sites appear when components are extended or configured by authors, not in the original design. This lab builds accessibility into the block itself: semantic HTML first, ARIA only where a pattern requires it, and validation before anything is published.

## Blocks

| Block | Pattern | Key WCAG criteria | Status |
|---|---|---|---|
| Accordion | Native `<details>/<summary>` | 2.1.1, 2.4.7, 4.1.2 | Planned |
| Tabs | WAI-ARIA APG Tabs | 1.3.1, 2.1.1, 2.4.3, 4.1.2 | Planned |
| Cards | Accessible card with single link target | 1.3.1, 2.4.4, 2.5.8 | Planned |
| Form | Labels, errors and status messages | 1.3.1, 3.3.1, 3.3.2, 4.1.3 | Planned |

## How each block is validated

1. **Keyboard:** full operation without a mouse, visible focus (2.4.7) and logical order (2.4.3).
2. **Screen reader:** tested with NVDA + Chrome; announcements documented per block.
3. **Automated checks:** axe-core with Playwright in CI (in progress). Automated tools catch only part of WCAG issues, so manual testing is always required.
4. **Performance:** Lighthouse budget kept at the boilerplate level.

Each block includes an accessibility sheet: criteria covered, keyboard map, screen reader output and known limitations.

## Tech stack

AEM Edge Delivery Services · `aem-boilerplate` · vanilla JavaScript and CSS · Document Authoring (da.live) · Playwright + axe-core.

## Run locally

1. `npm install`
2. `npm install -g @adobe/aem-cli`
3. `aem up` → http://localhost:3000

## About

Built by **Pamela Schurrer**, a front-end developer focused on digital accessibility (WCAG 2.2, EN 301 549), currently specialising in Adobe Experience Manager.
[Pamela Schurrer on LinkedIn](https://www.linkedin.com/in/pamela-celeste-schurrer/)

Based on [adobe/aem-boilerplate](https://github.com/adobe/aem-boilerplate) (Apache License 2.0).