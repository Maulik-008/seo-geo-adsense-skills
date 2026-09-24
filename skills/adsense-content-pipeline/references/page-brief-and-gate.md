# Page Brief and Publish Gate

## Brief (fill in before writing)

```yaml
url_or_slug: 
topic_cluster:            # one of the site's core topics
profile: blog-post        # CORE-EEAT profile: blog-post | how-to-guide | comparison | faq-page | product-review | best-of | alternative | landing-page | testimonial
reader: ""                # who, and what they already know
job: ""                   # what they must be able to do or decide afterwards
query_or_question: ""     # what they typed or thought before landing
what_this_adds: ""        # what the current top results miss, get wrong, or leave out
specifics:                # 3–5 concrete facts, numbers, mechanisms, or examples the page must carry
  - 
sources:                  # primary sources first, with dates for anything time-sensitive
  - 
first_hand_material: ""   # the author's real experience, data, screenshots, or cases; "none" is an allowed answer
authority_type: synthesis # first-hand | synthesis | reference (never fake first-hand)
ymyl: false               # health, money, legal, or safety → stricter bar
monetization: none        # none | affiliate | sponsored (→ disclosure, CORE-EEAT T04)
open_questions: []        # [TK] items for the owner
```

If `what_this_adds` or `specifics` is empty after research, the page should not be written yet. Narrow the topic or collect material first.

## Publish gate (all must hold)

**Truth and substance**

- [ ] No invented facts, stats, quotes, experiences, credentials, ratings, or dates. The `[TK]` list is empty or has been answered by the owner.
- [ ] Every claim that matters is traceable to a named source or to the owner's own material.
- [ ] The page states what it adds beyond the top results, and actually delivers it.

**CORE-EEAT audit (`content-quality-auditor`)**

- [ ] No veto: C01 (title promise), R10 (internal contradiction), T04 (undisclosed connection).
- [ ] No `fail` on C02 (direct answer), R04 (claims backed by evidence), or O09 (filler).
- [ ] Verdict is `SHIP`, or `FIX` where every remaining finding is Medium or lower under the local overrides.
- [ ] If the verdict is `UNDECIDED` only because site-level Authority items are `unknown`, the gate may pass on the observed items. Say so explicitly, and never report a score.

**Writing quality (`human-web-content` §13)**

- [ ] The final editorial checklist has been run. Anti-slop items are clean. No hallucinated markup (`oaicite`, `contentReference`, `turn0search`).

**AdSense content rules**

- [ ] On-topic for the site (`ADS-CONTENT-08`), original rather than copied or syndicated (`ADS-CONTENT-01/02`), and not dominated by ads or affiliate blocks (`ADS-CONTENT-05`).
- [ ] No prohibited or restricted content concerns (`ADS-PUB-*`, `ADS-REST-*`), or they have been resolved with the owner.

**Head and technical**

- [ ] Title and meta match the page (C01). JSON-LD uses only visible, true values (`serp-markup-builder`).
- [ ] The page is indexable, returns 200, is linked from navigation or a category, is in the sitemap, and works on mobile.
- [ ] A byline links to a real author page. A visible date appears where the topic is time-sensitive.

**Human review**

- [ ] The owner or an editor has read the final page.

Record the result in the tracker's page gate log: `pass`, or `fail — <first failing item>`.
