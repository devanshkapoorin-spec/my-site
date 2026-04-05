# Fix List — Prioritised
*Output of the 5-person expert panel review.*

---

## P0 — Launch Blockers
*Do not deploy without fixing these.*

### P0-1: Contact form is fake
**What:** The submit button runs a `setTimeout` that fakes success. No email is sent. Devansh receives zero contact attempts made through the site.
**Fix:** Wire to Formspree (free, 10 minutes). Replace the fake timeout with a real `fetch` to `https://formspree.io/f/{form-id}`. Keep the same success message UI.
**Who raised it:** Marcus, Ankit, Meera

### P0-2: No resume/CV download link
**What:** The single most common recruiter action on a portfolio site — downloading the CV — is not offered anywhere on the page. Not in the hero, not in the nav, not in the contact section.
**Fix:** Add a "Download CV" button as a third CTA in the hero, or replace the secondary "See the work" CTA. Also add a link in the contact aside. Host the PDF on Google Drive or directly in the repo.
**Who raised it:** Marcus, Ankit, Meera, Rahul

### P0-3: Form validation is silent
**What:** Submitting the form with empty required fields does nothing visible. The JS returns silently. Users have no idea why nothing happened.
**Fix:** On failed validation, add a visible error state — red border on empty required fields + an inline error message. At minimum, shake the submit button.
**Who raised it:** Marcus

---

## P1 — Important
*Fix before actively sharing the site.*

### P1-1: Stat counter animates single-digit "3"
**What:** The counter animation counts from 0 to 3 over 1.6 seconds for "Countries worked in." This looks like a loading bug, not a feature.
**Fix:** Add a minimum threshold — only animate counters where `data-target > 9`. For single-digit stats, render the number immediately.
**Who raised it:** Marcus

### P1-2: Project cards are dead ends — no artifacts
**What:** Four projects, none linkable. No PDFs, no GitHub, no published writing. A motivated recruiter has no way to verify or share the work.
**Fix:** Even one downloadable artifact (a methodology one-pager, a brief PDF, a GitHub notebook) would transform the projects section. Add a "View work →" link per card, even if some cards link to the same document initially.
**Who raised it:** Marcus, Meera, Rahul

### P1-3: Marquee ticker breaks hero momentum
**What:** The scrolling keywords strip sits between the Hero and About sections, creating a jarring tonal shift immediately after the strongest copy on the page.
**Fix:** Move it below the About section. Or below Projects. It works as a design element — the placement is the problem.
**Who raised it:** Ankit, Shreya

### P1-4: "Boston, MA" edu-badge is redundant
**What:** The education strip inside About shows a "Boston, MA" badge — but this is already in the sidebar block directly to its right. Duplicate information in adjacent elements looks unedited.
**Fix:** Remove the `.edu-badge` from the education strip. Replace it with something useful: the degree year, or a relevant course highlight, or nothing.
**Who raised it:** Marcus (structural), Meera (readability)

### P1-5: $500M World Bank claim is overframed
**What:** "World Bank initiative independently evaluated" implies hired involvement. It was an academic evaluation. Sophisticated readers — the target audience — will notice. Overselling kills credibility faster than underselling.
**Fix:** Change the stat label to "World Bank programme — academic evaluation" or change the project card description to "independent academic evaluation of..." This is a small word change with a large credibility impact.
**Who raised it:** Rahul, Meera

### P1-6: Hero stats are below the fold on most screens
**What:** The layout is badge → tag → H1 (3 lines at 80px) → subtext (4 lines) → CTAs → 88px margin → stats. On a ~900px tall laptop screen the stats (5M+ users, $500M) never appear without scrolling. These are the strongest proof points and they're hidden.
**Fix:** Reduce `margin-bottom` on `.hero-ctas` from 88px to ~44px. Or restructure to show one key stat inline near the subheadline.
**Who raised it:** Marcus, Ankit

---

## P2 — Nice to Have
*Improvements that would strengthen the site; do after P0/P1 are clear.*

### P2-1: No active nav state / scrollspy
**What:** As you scroll through sections, the nav links don't reflect your position. On a long single-page site, this is a navigability gap.
**Fix:** Implement a scrollspy using IntersectionObserver — add an `.active` class to the current section's nav link, style it with the gold accent.

### P2-2: Copy lacks a POV — inject one opinion
**What:** The hero promises a person with an edge. The rest of the site delivers a well-written profile. There are no opinions, no specific takes, nothing only Devansh could say.
**Fix:** Add one sentence in the About section that states a specific belief: about AI in economics, about data quality in emerging markets, about something. Make it specific enough that someone could disagree with it.
**Who raised it:** Shreya, Rahul

### P2-3: Personality is buried — bring it up the page
**What:** The most human content (cricket, football, the AI question at the bottom of the interests section) is in section 5 of 6. Most recruiters won't reach it.
**Fix:** Surface one personality signal earlier — in the About body, in the sidebar, or as a short line below the hero sub. Even "Currently: building AI workflows, watching too much football, finishing an economics degree" would do the job.
**Who raised it:** Shreya, Rahul, Ankit

### P2-4: The decorative "Economics." hero text is invisible
**What:** The CSS `::after` pseudo-element on `#hero` renders "Economics." at 4% opacity. At normal viewing distance and on most monitors, this is completely invisible. It adds nothing.
**Fix:** Either increase to 7–8% opacity so it reads as intentional, or remove it. Half-visible design elements look like bugs.
**Who raised it:** Marcus

### P2-5: Services framing doesn't match the product
**What:** Calling these "capabilities" works. But the three capability titles (Research & Policy Analysis / Data & Economic Analysis / Financial Modelling & Strategy) are generic across every economics graduate. They're what he's listing, not what makes his version of these things distinctive.
**Fix:** Consider tightening each title to include something specific: "Policy Research — regulatory & stakeholder" / "Economic Analysis — field-built datasets" / "Financial Modelling — audit-ready outputs." Small specificity gain, large distinctiveness gain.
**Who raised it:** Shreya, Rahul

### P2-6: `--accent-mid` CSS variable is defined but unused
**What:** Dead code in the design tokens. Minor but reflects an untidy stylesheet.
**Fix:** Remove the variable or use it somewhere intentionally.
**Who raised it:** Marcus

### P2-7: Add `<meta name="theme-color">` for mobile browsers
**What:** Without this, the browser chrome on mobile defaults to white instead of matching the cream site background.
**Fix:** Add `<meta name="theme-color" content="#f5f2eb">` to the `<head>`.
**Who raised it:** Marcus

---

## Summary table

| ID | Issue | Priority | Effort |
|---|---|---|---|
| P0-1 | Fake contact form | P0 | Low (Formspree) |
| P0-2 | No resume download | P0 | Low |
| P0-3 | Silent form validation | P0 | Low |
| P1-1 | Single-digit counter animation | P1 | Low |
| P1-2 | Project cards have no artifacts | P1 | Medium |
| P1-3 | Marquee placement breaks momentum | P1 | Low |
| P1-4 | Redundant edu-badge | P1 | Trivial |
| P1-5 | $500M claim overframed | P1 | Trivial (2 words) |
| P1-6 | Stats below fold | P1 | Low |
| P2-1 | No scrollspy/active nav | P2 | Medium |
| P2-2 | No POV in copy | P2 | Medium (writing) |
| P2-3 | Personality buried | P2 | Medium (writing) |
| P2-4 | Invisible decorative text | P2 | Trivial |
| P2-5 | Generic service titles | P2 | Low |
| P2-6 | Dead CSS variable | P2 | Trivial |
| P2-7 | Missing theme-color meta | P2 | Trivial |
