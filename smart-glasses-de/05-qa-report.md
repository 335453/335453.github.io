# QA Report — WERKBLICK Smart-Glasses Landing-Page Demo

**Newagent / QA stage | 20 November 2026**  
**Reviewed:** `01-research.md`, `02-strategy.md`, `03-copywriting.md`, and `04-prototype/index.html`.  
**Methods:** HTML parser inspection; Python/BeautifulSoup link validation; Chromium rendering via Playwright `set_content` from the exact HTML source; functional button tests at 1440 × 900 desktop and 390 × 844 mobile viewports; visual screenshot review. These are real Chromium browser checks, **not** a deployed website test or smart-glasses hardware test.

## 🔴 Must fix before delivery

**None detected.**

## 🟡 Recommended improvements / limitations

1. **Not a sales lead-generation system.** The CTA expands a copyable internal-request template rather than sending a contact form. This is intentional for an unlaunched concept and avoids collecting personal data; a production service would need a legitimate contact mechanism, privacy notice and consent/legal basis as applicable.
2. **Trademark and entity status.** WERKBLICK is a working title only; formal DPMA/EUIPO/WIPO search and domain availability were not completed. The demo appropriately discloses this, but do not commercially publish as a brand until resolved.
3. **No hardware/backend integration.** The animated stepper is a representative browser interaction and not a tested headset app. An actual hardware pairing, speech interface, network handling, WMS/MES integration, and safety assessment remain open.
4. **Accessibility and field usability.** Good basic HTML semantics and focus-visible rules, but keyboard-only, screen-reader and device-specific vision/ergonomics testing were not run comprehensively. Test with target users before publication.
5. **Language / mobile visual density.** Narrow-layout screenshots are readable at source viewport width and have no horizontal overflow; however, German copy is text-heavy and could benefit from shorter sentences on small screens.

## 🟢 Passed checks

| Test | Result / evidence |
|---|---|
| HTML source / semantic layout | Contains doctype, `lang="de"`, header, nav, main, sections and footer; parsed without blocker |
| Standalone file | No linked external scripts, style sheets, fonts or image dependencies; CSS and JavaScript embedded |
| Internal links | All anchor fragment targets exist; zero empty or `href="#"` links |
| Content vs strategy | One-workflow, six-week pilot, baseline and go/no-go decision consistent with strategy and copy |
| No invented proof | No sales, customers, specific savings, vendor relationships, legal certification or guaranteed device compatibility claimed |
| Privacy scope | Camera-free starting inspection scenario, employee representation and legal reviews appropriately qualified |
| Desktop layout | Chromium at 1440 × 900: document width 1440 px; no horizontal overflow, no JavaScript page errors |
| Mobile layout | Chromium at 390 × 844: document width 390 px; no horizontal overflow, no JavaScript page errors |
| Demo interaction | Next advances 1→2→3 and cycles to 1; initial Back is disabled; tested at both sizes |
| CTA interaction | Opening the inquiry template makes it visible and sets `aria-expanded=true`; toggle back hides it; tested at both sizes |
| Screenshot review | Hero, 4 benefit cards, pilot timeline, demo and CTA remain visually distinct on desktop and in a vertically stacked mobile layout |

**Additional output:** `preview-desktop.png` and `preview-mobile.png` are actual Chromium renders of the HTML source.

## Fix–verify rounds

- **Round 0 (initial QA):** no red findings. No change/retest rounds required.
- Clipboard permission handling is implemented with a manual-selection fallback but was not independently exercised in the automated click tests; report as **not verified**, not passed.

## Verdict

**PASS for a static educational/demo landing page. NOT production-ready.** No red content or interaction blockers discovered in the tests above. Hardware, security, legal, trademark and commercial acceptance are untested.
