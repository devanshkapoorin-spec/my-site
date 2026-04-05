# Panel Discussion — Devansh Kapoor Portfolio Review

*All five panellists, after reading each other's independent reviews.*

---

**Ankit:** I want to start with the thing we all independently flagged and didn't coordinate on: there is no resume download. Five of us noticed it independently. That tells you something. It's not a design preference — it's a functional gap that costs conversions every single day this site is live without it.

**Meera:** It's the first thing I look for. Before I read a word. If I have to dig for it, I'm already forming an impression about attention to detail. And the impression isn't great.

**Marcus:** Agreed, and I'll add the equally critical thing: the contact form sends a fake success message. There's a `setTimeout` in the JavaScript that pretends to send. If someone actually fills out that form — a recruiter, a hiring manager — Devansh gets nothing. He doesn't even know they tried. You can wire this to Formspree in 10 minutes for free. This is a launch blocker, not a polish issue.

**Shreya:** I want to acknowledge what's working before we get too negative. The headline is genuinely good. "I've never been satisfied just describing a market" — that's a real voice. It's the line that made me keep reading. And the interests section, particularly the football and cricket bits, shows personality that the rest of the site could learn from.

**Rahul:** The interests section is actually my favourite part of the site and it's section 5 of 6. That's the personality problem in a nutshell.

**Ankit:** Yes. The page is structured like a story, not a conversion funnel. The most human, memorable material — the football research line, the cricket club story — is at the bottom. Recruiter attention drops exponentially with scroll depth. The stuff that makes this person *memorable* is where the fewest eyes land.

**Shreya:** And the copy goes cold exactly when it should be warming up. After the hero — which is strong — the About section shifts into this slightly elevated register. "Rigour, range, and the willingness to build the framework." That's corporate paraphrase of a personality, not the personality itself.

**Rahul:** I'll push back slightly. The about copy isn't bad. It's the *absence* of a point of view that's the problem. What does Devansh actually think about something in his domain? The AI interests section has his most interesting question — "what does this actually change about how economists work?" — and it's buried under a cricket card. That question, placed in the hero or the about, would make this site memorable.

**Meera:** The things I kept coming back to as the hiring manager: no resume, no links from the project cards, and the $500M World Bank claim. Rahul is right that a sophisticated reader will notice the framing is doing some work there. It's not wrong, but it's positioned as more significant than a student research project usually is.

**Rahul:** To be fair to Devansh, evaluating a real $500M programme against academic literature is more impressive than most undergrad work. The work is real. The framing just needs to be a touch more honest — "independent academic evaluation" rather than the implied "I worked with the World Bank."

**Marcus:** From a design standpoint, the project cards are dead ends. Four projects, none of them have a link, a PDF, a GitHub link, anything. On a portfolio site, a project card without an artifact is just a claim. The claims are good. But one downloadable PDF of any of these projects would do more for credibility than all four combined.

**Ankit:** The marquee ticker placement is also bothering me. It sits between the hero and the About section and completely breaks the emotional momentum. You just read "I've never been satisfied just describing a market" and then you hit a rotating scrolling list of "ECONOMETRICS · STAKEHOLDER MAPPING" in muted grey caps. It's a tonal car crash.

**Shreya:** Yes. Move it below About. Or below Projects. It works as a design element but not where it is.

**Marcus:** One more technical thing: the stat counter animates the number "3" from zero. It counts: 0, 1, 2, 3. For a single-digit number this looks like a bug, not a feature. The other stats — 10K+, 5M+, $500M — the counter animation works for those. But for "3 countries," just show the number.

---

## What we agree on

**Things that are working:**
- The hero headline is genuinely distinctive
- The editorial design system — the typography, the cream background, the gold accent — is well-executed and appropriate for the target audience
- The stats row is the right instinct; the numbers are real proof points
- The interests section shows the personality the rest of the site lacks
- The international thread (India, Indonesia, US) is a real differentiator and is well-surfaced in the hero

**Things that must change before deployment:**
1. Wire the contact form to a real endpoint
2. Add a resume download — in the hero, not buried in the contact section
3. Fix the counter animation for the "3 countries" stat
4. Fix silent form validation — show errors when fields are missing
5. Add at least one clickable artifact to the projects section
6. Move or reframe the $500M World Bank claim

**Things that would significantly improve the site:**
7. Add Devansh's actual point of view on something in his domain
8. Move the marquee ticker — below About, not between Hero and About
9. Bring personality elements earlier in the page flow
10. Add an active nav state / scrollspy
