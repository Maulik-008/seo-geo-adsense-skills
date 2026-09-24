# Rejection and "Needs attention" Playbook

Start from the **exact text** on the AdSense **Sites** page (and the Policy center, if the site is approved but restricted). The wording changes over time. Match it by meaning, and check the current explanation in AdSense Help: https://support.google.com/adsense/answer/7299563?hl=en

General rules:

- A rejection is almost always a **site-level** judgement. Fixing one article rarely changes it.
- Fix the cause, re-run `adsense-auditor` in full, and request review again only when there are no Blockers.
- Do not request review repeatedly without real changes.
- Keep the site live and crawlable during review.

## Common messages → likely causes → actions

| Message (meaning) | Likely causes | Check (IDs) | Action (skill) |
|---|---|---|---|
| **Low value content** | Thin or generic pages; AI-generic or reworded content; off-topic spread; too little that is useful yet; pages built for search or ads | `ADS-CONTENT-01/02/03/08`, `ADS-PUB-11` | Phase 2 triage (remove, merge, improve), then the Phase 4 loop on core pages (`human-web-content` → `content-quality-auditor`). Narrow the focus. Add the owner's real material. |
| **Valuable inventory: no content** | Pages the crawler saw have little or no main content; heavy JS rendering; empty templates | `ADS-CONTENT-03`, `ADS-OWN-03`, `ADS-CRAWL-01` | Confirm the main content is in the rendered HTML; fix empty templates and archives; check that key pages don't need login or POST. |
| **Valuable inventory: under construction** | "Coming soon" sections, placeholders, broken navigation targets, unfinished categories | `ADS-CONTENT-04`, `ADS-UX-03` | Remove or finish every placeholder; remove empty nav items. |
| **Valuable inventory: scraped / copied content** | Copied, syndicated, auto-imported, or lightly reworded pages; embed-only posts | `ADS-CONTENT-02`, `ADS-PUB-02` | Remove or rewrite from scratch; add original analysis; cite sources. Never "spin" the pages. |
| **Site down or unavailable** | Downtime, DNS/TLS problems, WAF or bot protection blocking Google, geoblocking | `ADS-CRAWL-01/02/06` | Fetch the pages as a crawler would; check `robots.txt` for `Mediapartners-Google`; whitelist Google in the WAF/CDN; fix DNS and TLS. |
| **Policy violations** | Content in a prohibited category; deceptive UX; copyright problems; misrepresentation | `ADS-PUB-01…16`, `ADS-UX-03/04` | Identify the pages concerned (Policy center); remove or fix them; fix the site identity and disclosures. Scope with the owner. |
| **Navigation / site behaviour problems** | Broken menus; misleading buttons; pop-ups; redirects; hard to find content | `ADS-UX-01…04`, `ADS-CRAWL-04` | Test desktop and mobile; remove obstructive overlays; fix the redirect chains. |
| **Couldn't verify the site / ownership** | AdSense code not in `<head>`; wrong domain variant (www vs non-www, or subdomain); the site not added correctly | `ADS-OWN-01/02`, `ADS-SITE-01/02` | Confirm the code is on every page's `<head>` and the domain matches exactly; use the verification method shown in AdSense. |
| **Getting ready (for a long time)** | Review is still in progress | — | Keep the site live and unchanged in structure. Keep publishing real pages at a normal pace. Don't re-apply. |
| **ads.txt status: not found / unauthorized** | Missing file, or wrong publisher ID | `ADS-TXT-01/02` | Serve `/ads.txt` at the root domain with the exact line shown in AdSense. |

## Recovery plan template

```markdown
### Rejection recovery — <site> — <date>
Exact message: "<paste>"
Mapped IDs: …
Root cause (site-level): …

Fixes
1. <fix> — owner / skill — done?
2. …

Evidence it is fixed: <re-audit summary: Blockers 0, High n (accepted: …)>
Ready to request review: yes / no (reason)
Reminder: approval is Google's decision; this is readiness, not a guarantee.
```
