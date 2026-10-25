# Accessible EDS Blocks: Guide

A guide to building accessible blocks for Adobe Experience Manager Edge Delivery Services (EDS). Each block documents the pattern it follows, the WCAG criteria it addresses, how it behaves with keyboard and screen reader, and what content authors must do to keep it accessible.

## Standard

- **WCAG 2.2, Level AA.**
- **EN 301 549**, the European standard for ICT accessibility referenced by the European Accessibility Act and Spanish Law 11/2023. Its web requirements map to WCAG Level A and AA success criteria.

## Principles

1. **Native HTML first.** Use `<button>`, `<details>`, `<nav>` and real headings before adding ARIA.
2. **APG patterns for custom widgets.** When no native element fits (tabs, carousel), follow the W3C ARIA Authoring Practices Guide.
3. **Accessibility lives in the block and in the authoring.** Most failures come from content (alt text, link text, heading levels), so every block includes authoring rules.
4. **Automated tests are not enough.** Lighthouse 100 and a clean axe report do not mean a block is accessible; keyboard and screen reader testing are required.

## Blocks

| Block | Pattern | Status |
|---|---|---|
| Accordion | Native `<details>` / `<summary>` | Planned |
| Tabs | APG Tabs (automatic activation) | Planned |
| Cards | Native list + single link per card | Planned |
| Form | Native form controls, labelled errors | Planned |

**Status:** *Planned* (not built or not tested) · *In progress* (built, testing under way) · *Validated* (passes axe in CI, keyboard and screen reader tests).

## What each block documents

Each block includes a `README.md` in `blocks/<name>/` with:

1. **Pattern**: the native element or APG pattern used.
2. **WCAG criteria**: number, name and level.
3. **Keyboard map**: every key and what it does.
4. **Screen reader output**: what NVDA announces.
5. **Authoring rules**: what content authors must do.
6. **Known limitations**.

## Testing approach

| Layer | Method | Main criteria |
|---|---|---|
| Automated | axe-core with Playwright in CI | Subset of A/AA failures |
| Keyboard | Tab, Shift+Tab, Enter, Space, arrows, Escape | 2.1.1, 2.1.2, 2.4.3, 2.4.7 |
| Screen reader | NVDA with Chrome and Firefox (Windows) | 1.3.1, 4.1.2, 4.1.3 |
| Visual | 200% / 400% zoom, 320 px viewport, contrast | 1.4.3, 1.4.10, 1.4.11, 2.5.8 |
| Motion | `prefers-reduced-motion` | 2.3.3 (AAA, good practice) |

## Feedback

If you find an accessibility issue, please open a GitHub issue with the page URL, the browser and assistive technology used, and what happened.