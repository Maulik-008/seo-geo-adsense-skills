# Human Title and Snippet Rules (local)

Local addition (2026-09-24). This is not upstream. **These rules override the title and description formulas in `meta-tag-formulas.md` and `ctr-and-social-reference.md`.** Those formulas ("The Complete Guide ([Year])", "Ultimate", "Here's…", brackets, and power words) are the pattern that makes titles read as machine-written, and the CTR percentages attached to them are unverified.

## The test

Read the title aloud. **Would a knowledgeable person say this to a friend who asked the question?** If it sounds like an ad, a YouTube thumbnail, or a template with the blanks filled in, rewrite it.

A good title:

1. Names the real subject in the words the reader would search for.
2. Says what the page does for them: answers, compares, shows how, or lists.
3. Carries one true specific when it helps (a version, a place, a real count, a tax year).
4. Promises exactly what the page delivers. A mismatch is a CORE-EEAT C01 veto.

## How Google treats these tags (facts to respect)

- Google has no fixed character limit. It truncates by pixel width, so aim for roughly **50–60 characters** before the brand. Put the important words first *when that still reads naturally*.
- Google may rewrite a title link that is keyword-stuffed, boilerplate, too long, or unrelated to the page's main heading. Honest, specific titles that match the H1 are rewritten least.
- Every indexable page needs a **unique** title and description.
- The meta description is not a ranking factor, and Google often shows page text instead. Write it for a human deciding whether to click, in about **140–160 characters**.
- `meta keywords` is ignored. Do not write one.
- Source: Google Search Central, "Influencing your title links" and "Control your snippets". Check the live pages when unsure.

## Title bans

Never use these unless the words are literally true and ordinary for the topic:

- **Hype words:** Ultimate, Complete Guide, Definitive, Everything You Need to Know, Master, Unlock, Supercharge, Game-Changer, Secret(s), Hack(s), Mind-Blowing, Proven, Insane, Must-Know.
- **Template tails:** ": A Comprehensive Guide", ": Tips and Tricks", ": All You Need to Know", "(Expert Tips)", "[Updated]", "(Step-by-Step)" when the page is not steps.
- **Question plus reveal:** "What Is X? Here's What You Need to Know", "Why X? Here's Why".
- **Clickbait and mystery:** "You Won't Believe", "The Hidden Cost of…", "What Nobody Tells You About…", "…Is Getting This Wrong".
- **A year** unless the content is bound to that year and was actually updated for it (tax year, price list, exam cycle).
- **A number** unless the page has exactly that many items. Never round up to 10.
- **Formatting:** ALL CAPS, emoji, exclamation marks, and more than one separator.
- **Stuffing:** the same keyword twice, or a keyword list joined with pipes.
- **Rule-of-three filler:** "Tips, Tricks, and Strategies".

## Description bans

- Openers such as "Learn…", "Discover…", "In this article…", "This guide…", "Looking for…?", or "Are you…?"
- "Click here", "Read more", "Find out now", and other empty CTAs. A CTA is fine only when it names a real action, such as "Download the free GST invoice template."
- Claims the page does not make: "We tested", "Trusted by thousands", "Expert-reviewed". Use them only if they are visibly true on the page.
- The words banned in human-web-content §9.1 (delve, leverage, seamless, robust, comprehensive, …).

## What to do instead

| Page | Weak (AI-template) | Human |
|---|---|---|
| How-to | How to File GST Returns: The Complete Guide (2026) | How to File GSTR-1 as a Freelancer, Step by Step |
| Question | What Is TDS? Here's Everything You Need to Know | What TDS Is and When It's Deducted From Your Pay |
| Comparison | Zoho vs Tally: Which Is the Ultimate Choice? | Zoho Books vs Tally Prime for a Two-Person Business |
| List | 10 Best Budget Laptops You Won't Believe Exist | 7 Laptops Under ₹50,000 That Handle Video Editing |
| Problem | Why Your Website Is Slow (And How to Fix It!) | Why WordPress Sites Load Slowly on Shared Hosting |

*(These rows are illustrative patterns, not claims. A real page's specifics must come from the page.)*

Descriptions follow the same idea: say what the page answers and for whom, in one or two plain sentences, with one concrete detail.

> Weak: "Discover everything you need to know about GST filing with our comprehensive guide. Click here to learn more!"
> Human: "Which GSTR forms a freelancer files, the monthly and quarterly deadlines, and the late fee if you miss one."

## The other SERP pieces

- **H1:** it may differ from the title, but it must promise the same thing. One H1 per page.
- **Slug:** short, lowercase, hyphenated, and containing the main term (`/gstr-1-freelancers`). No dates unless the page is date-bound. Don't change slugs on live pages without a 301 redirect.
- **Brand:** at the end (`… | Brand`) when there is room. On the homepage, lead with the brand plus what the site is.
- **OG / Twitter title:** it may be slightly more conversational than the title tag. It follows the same truth and ban rules.
- **Image alt:** describe what the image shows for someone who can't see it. No keyword lists. Decorative images get `alt=""`.
- **Indian English:** follow human-web-content §8. Natural and correct; ₹ and lakh/crore where readers expect them.

## Self-check (run on every title and description)

- [ ] It passes the read-aloud test.
- [ ] It contains nothing from the ban lists.
- [ ] Every number, year, and claim is true on the page.
- [ ] The title is about 50–60 characters before the brand, and the description about 140–160 characters (count them; don't estimate).
- [ ] The title matches the H1's promise and the page's intent.
- [ ] It is unique across the site or batch.
- [ ] The keyword appears once, naturally.
