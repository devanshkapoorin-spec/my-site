# Marcus Tan — Product Designer Review

**TL;DR:** The design has real craft. The typography system is solid, the whitespace is disciplined, the interactions are thoughtful. But there are five functional bugs that would embarrass this site in front of a recruiter, and two structural hierarchy problems that are bleeding conversion.

---

## Genuine strengths

- Typographic scale is excellent — Playfair Display for headlines, Inter for body, consistent sizing rhythm
- The dot-grid hero background is tasteful, not gimmicky
- Scroll animations are well-timed and don't fight the content
- Service card `::before` / `::after` hover effects are genuinely polished
- Mobile breakpoints are thoughtfully handled — grids collapse cleanly

---

## Functional bugs (things that are actually broken)

**Bug 1 — The contact form is fake.**
The submit button calls a `setTimeout` that shows a success message and resets the form. No email is sent. No backend. No Formspree, no Netlify Forms, nothing. If a recruiter fills this out and clicks Send, Devansh hears nothing. This is a launch blocker — full stop.

**Bug 2 — Form validation is silent.**
If you submit the form with empty required fields, the JS validation (`if (!name || !email || !message) return;`) does nothing visible to the user. The button doesn't shake, no error message appears, nothing turns red. The user has no idea why nothing happened. They probably try once, get confused, and leave.

**Bug 3 — The stat counter animates "3" for Countries.**
The animated counter counts from 0 to 3 over 1.6 seconds. Watching a number go 0 → 1 → 2 → 3 looks broken, not impressive. Counters make sense for numbers like 10,000 or 300,000. For single digits, just show the number.

**Bug 4 — The `font-display: swap` is missing in CSS.**
The Google Fonts URL does include it, but SVG text elements inside the inline logo don't reliably pick up web fonts before paint — there'll be a brief Georgia flash on load. Minor but noticeable on the logo.

**Bug 5 — `--accent-mid` is defined in `:root` but used nowhere in the stylesheet.** Dead variable.

---

## Hierarchy problems

**Problem 1 — The stats row is below the fold on most laptops.**
The hero has: badge → tag → h1 (3 lines at 80px) → subtext (4 lines) → two CTAs → 88px margin → stats. On a 900px-tall screen, the stats (5M+ users, $500M) never appear without scrolling. These are the strongest credibility signals on the page and they're hidden. The margin-bottom on `.hero-ctas` needs to drop from 88px to ~48px, or the stats need to move up.

**Problem 2 — No active nav state.**
As you scroll through the page, none of the nav links highlight to show your position. This is a navigability issue on a long single-page site. Easy fix with a scrollspy pattern.

---

## Smaller issues

- The decorative `::after` "Economics." text on the hero is at 4% opacity. I cannot actually see it at a normal viewing distance. It adds zero visual value. Remove or increase to at least 6–8%.
- No skip-to-content link — minor accessibility miss.
- No `<meta name="theme-color">` — affects browser chrome on mobile.
- Project cards have no links and no signal that there's more to see (no arrow, no "read more"). They look like dead ends.
- Resume download: not present anywhere. This is the most common recruiter action after landing on a portfolio site.

---

## Summary

The design is 80% of the way to production-ready. Fix the fake form, fix the silent validation, kill the single-digit counter animation, and move the stats row up. Those four changes alone would meaningfully improve the site's effectiveness.
