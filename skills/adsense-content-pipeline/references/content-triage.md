# Content Inventory and Triage

AdSense review looks at the **site**, not only your best article. A handful of strong posts next to dozens of thin, off-topic, or template pages still reads as a low-value site. Triage happens before new writing.

## 1. Define the focus

Write down:

- **Purpose:** one sentence on what this site does for whom. Example: "Practical GST and income-tax guides for freelancers in India."
- **Core topics:** 3–6. Everything published should sit under one of them.
- **Out of scope:** topics the site will not cover.

A site that covers "tech, health, cricket, recipes, and finance" with no reason to connect them matches Google's warning sign of "publishing across many unrelated topics hoping something ranks". Narrow it, or split it into separate sites.

## 2. Inventory

List every URL a visitor or crawler can reach: posts, pages, category/tag archives, author pages, search pages, attachment pages, and paginated lists. Sources: the sitemap, the CMS export, a crawl, and navigation.

Record for each URL: title, type, topic, word count (as a rough signal only), last updated, whether it has original substance, whether it is linked from navigation, and whether it is indexable.

## 3. Classify

| Class | Signal | Action |
|---|---|---|
| **Keep** | Useful, original, accurate, on-topic | Light fixes: dates, links, markup. |
| **Improve** | Right topic and intent, but thin, vague, stale, or generic | Rewrite with `human-web-content` (§5: cut, verify, add substance). Run it through the gate. |
| **Merge** | Several near-duplicate or overlapping pages on one question | Combine into one strong page and 301 the others to it. |
| **Rewrite** | Copied, spun, or AI-generic filler on a topic the site should cover | Start over from a real brief. Never reword a competitor page. |
| **Remove** | Off-topic, placeholder, "coming soon", empty archives, scraped or auto-generated, affiliate-only with no commentary | Delete it (return 404/410, or 301 if a real equivalent exists) and remove it from navigation and the sitemap. |

Thin-content signals, mapped to AdSense IDs:

- Empty or near-empty pages, lorem ipsum, "coming soon" → `ADS-CONTENT-04`
- Tag/category archives with no introduction and a handful of links → `ADS-CONTENT-03`
- Copied, syndicated, embed-only, or feed pages with nothing added → `ADS-CONTENT-02`
- Templated "best X in [city]" sets that swap only a variable → `ADS-CONTENT-08` (doorway pages)
- Ads or affiliate blocks outweighing the content → `ADS-CONTENT-05`

About `noindex`: it keeps a page out of Search results, but the page stays reachable. If it is linked from navigation or the sitemap, a reviewer can still land on it. For weak pages, improving or removing them beats noindexing them. Reserve `noindex` for pages that are useful to visitors but not search-worthy, such as internal search results or thank-you pages.

## 4. How many pages?

Google publishes **no minimum post count or word count** for AdSense. Numbers like "30 posts of 1,000 words" are folklore, and padding to hit them makes things worse. The working test:

- Every navigation section leads to real, substantial pages.
- A first-time visitor can tell what the site is for, and find enough to satisfy that purpose.
- Nothing linked from the site looks unfinished.

When a site has few pages, fewer strong pages beat many thin ones. Be honest with the user when the site is simply too early: the fix is time and real content, not tricks.

## 5. Output

```markdown
### Site focus
Purpose: …
Core topics: …
Out of scope: …

### Triage summary
keep n · improve n · merge n (→ targets) · rewrite n · remove n

| URL | Class | Reason (ID) | Action | Owner input needed |
|---|---|---|---|---|

### Core page plan (new pages)
| Working title | Topic | Reader and job | Why this site can write it | Sources / first-hand material |
|---|---|---|---|---|
```
