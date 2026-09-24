# AdSense Website Requirements Checklist

73 requirement IDs across sections A–I. Section J is the output format. Every ID must appear
exactly once in an audit's final checklist table.

## Source URLs (Google official — English)

**AdSense**
- AdSense Help home: https://support.google.com/adsense/
- Ensure your pages are ready for AdSense review: https://support.google.com/adsense/answer/7299563?hl=en
- AdSense eligibility requirements: https://support.google.com/adsense/answer/9724?hl=en
- Site ownership: https://support.google.com/adsense/answer/91205?hl=en
- Manage your sites in AdSense: https://support.google.com/adsense/answer/12131223?hl=en
- Add a site to AdSense: https://support.google.com/adsense/answer/9784409?hl=en
- Fix AdSense crawler errors / "AdSense crawler can't access your page": https://support.google.com/adsense/answer/2381908?hl=en
- Set up ads.txt: https://support.google.com/adsense/answer/12171612?hl=en
- Ad placement policies (implementation): https://support.google.com/adsense/answer/1346295?hl=en
- Invalid traffic / invalid clicks: https://support.google.com/adsense/answer/16737?hl=en

**Policies**
- AdSense Program policies: https://support.google.com/adsense/answer/48182?hl=en
- Google Publisher Policies: https://support.google.com/publisherpolicies/answer/10502938?hl=en
- Google Publisher Restrictions: https://support.google.com/publisherpolicies/answer/10437795?hl=en
- Publisher Policies — overview / all articles: https://support.google.com/publisherpolicies/
- Personalized advertising (restricted data / sensitive categories): https://support.google.com/adspolicy/answer/143465?hl=en

**Privacy / consent**
- Google's EU user consent policy: https://www.google.com/about/company/user-consent-policy/
- Required minimum functionality for CMPs (Google-certified CMP): https://support.google.com/adsense/answer/13554116?hl=en
- Cookies / how Google uses data on partner sites: https://policies.google.com/technologies/partner-sites
- COPPA / child-directed treatment (tag for child-directed treatment): https://support.google.com/admob/answer/6223431?hl=en

> If a link 404s, search the phrase in the article title on `support.google.com` and use the
> current English page. The live Google doc always wins over this file.

## Severity

- `Blocker` — hard policy violation, ownership/crawl failure, no original content, severe
  deceptive UX, prohibited content, or the application cannot be verified.
- `High` — likely review failure or ad-serving restriction, but not always a hard account-level
  block.
- `Medium` — a quality, trust, UX, disclosure, or implementation gap to fix before applying.
- `Unknown` — needs owner / account / server access, or more pages, to verify.

---

## A. Eligibility and account requirements

| ID | Severity | Requirement | Check |
| --- | --- | --- | --- |
| ADS-ELIG-01 | Blocker | The applicant must be eligible for AdSense and generally at least 18 years old, or use a parent / guardian's account when under 18. | Ask / confirm owner and account context. |
| ADS-ELIG-02 | Blocker | Do not create duplicate AdSense accounts for the same publisher. Add more sites to the existing account, unless a genuinely distinct legal entity applies. | Ask whether an AdSense account already exists for this person or company. |
| ADS-ELIG-03 | Blocker | Site content must comply with the AdSense Program policies and the Google Publisher Policies before applying. | Run sections C–I. |
| ADS-ELIG-04 | Medium | Hosted products such as Blogger and YouTube use separate hosted-account flows and eligibility. | Note if the site is Blogger / YouTube / a hosted partner. |

## B. Site ownership, verification, and readiness

| ID | Severity | Requirement | Check |
| --- | --- | --- | --- |
| ADS-OWN-01 | Blocker | The publisher must control the site and be able to edit the HTML source or the CMS / theme / plugin path needed to place AdSense code in `<head>`. | Confirm repo / CMS / template access and a working `<head>` injection path. |
| ADS-OWN-02 | Blocker | Do not apply with a site the publisher does not own or cannot verify. | Confirm domain and control ownership. |
| ADS-OWN-03 | High | The site must render with JavaScript enabled and normal browser rendering so AdSense code can run. | Check pages render with JS on and do not break the `<head>` / `<body>` structure. |
| ADS-SITE-01 | Blocker | A site must be added to the AdSense **Sites** list, ownership verified, reviewed by Google, and marked **Ready** before ads can show. | For an account audit, check the AdSense Sites status if accessible, plus the stated policy issue. |
| ADS-SITE-02 | High | Ownership can be verified by the AdSense code snippet, an `ads.txt` line, or a meta tag, depending on the flow shown. | Confirm at least one verification method can be deployed. |
| ADS-TXT-01 | High | If the domain uses `ads.txt`, Google must be listed as an authorized seller for this account's publisher ID. | Fetch `/ads.txt`; check for the correct `google.com, pub-XXXXXXXX, DIRECT, f08c47fec0942fa0` line once the publisher ID exists. |
| ADS-TXT-02 | Medium | Publishing `ads.txt` is recommended to stop unauthorized sale of the site's ad inventory. | Recommend adding it once the AdSense publisher ID is known. |

## C. Content quality and site value

| ID | Severity | Requirement | Check |
| --- | --- | --- | --- |
| ADS-CONTENT-01 | Blocker | The site must have useful, original, visitor-relevant content. | Sample key pages. Reject scraped, AI-spun, doorway, placeholder, or auto-generated pages with no added value. |
| ADS-CONTENT-02 | Blocker | Do not rely on copied articles, embed-only videos, syndicated content, or affiliate feeds without original commentary, curation, review, data, tools, or analysis. | Compare templates and page bodies; check for duplicate snippets and source attribution. |
| ADS-CONTENT-03 | High | Main content must be substantial for users and crawlers — not only navigation, tags, listings, empty galleries, or thin pages. | Check the homepage, category / list pages, and detail pages. |
| ADS-CONTENT-04 | High | The site must not be under construction, empty, or built only to display ads. | Check for broken sections, lorem ipsum, "coming soon" blocks, dead links. |
| ADS-CONTENT-05 | High | Ads, affiliate blocks, sponsored listings, and paid promotion must not exceed or dominate the publisher's own content. | Estimate the above-the-fold ratio and the whole-page ratio. |
| ADS-CONTENT-06 | Medium | The main content language must be supported by AdSense. | Identify the site's primary language; check that mixed-language pages have real content. |
| ADS-CONTENT-07 | Medium | Comment sections and other user-generated content must be moderated for policy compliance. | Check visible comments, the review workflow, spam, and adult / offensive links. |
| ADS-CONTENT-08 | Medium | Content must not use excessive keyword repetition, doorway pages, or pages built mainly for search engines. | Inspect title / H1 / body patterns and near-duplicate internal pages. |

## D. Navigation, UX, and trust signals

| ID | Severity | Requirement | Check |
| --- | --- | --- | --- |
| ADS-UX-01 | High | Navigation must be clear, readable, aligned, and functional. | Test header, menus, dropdowns, and footer links on desktop and mobile. |
| ADS-UX-02 | High | A user must be able to tell what the site is, find content, and move between sections without misleading paths. | Check the homepage → category → detail flow, plus breadcrumbs / search. |
| ADS-UX-03 | Blocker | Do not use deceptive navigation, fake download / play buttons, links to content that does not exist, irrelevant redirects, or ads placed where navigation normally sits. | Inspect CTAs, buttons, ad placeholders, and redirects. |
| ADS-UX-04 | Blocker | Site behavior must not change user settings, redirect unexpectedly, trigger downloads, carry malware, or use obstructive pop-ups / pop-unders. | Test page load, clicks, mobile overlays, and third-party scripts. |
| ADS-UX-05 | Medium | Provide the trust pages appropriate to the site: About, Contact, Privacy Policy, and Terms / Disclaimer where relevant. | Verify the pages are real, reachable, and not boilerplate-only. |
| ADS-UX-06 | Medium | Avoid an intrusive ad-like layout before approval; do not blur the line between ads and content. | Check the visual hierarchy and any ad labels. |

## E. Crawlability, access, and technical availability

| ID | Severity | Requirement | Check |
| --- | --- | --- | --- |
| ADS-CRAWL-01 | Blocker | The site must be live and publicly reachable; key URLs must not return 404 or 5xx. | Fetch the homepage and representative pages with `curl` or a browser. |
| ADS-CRAWL-02 | Blocker | The AdSense crawler (`Mediapartners-Google`) must not be blocked by login walls, IP restrictions, geoblocking, WAF rules, or `robots.txt`. | Check public access, `robots.txt`, and firewall / bot-protection symptoms. |
| ADS-CRAWL-03 | High | Do not require POST data to view ad-bearing pages; the crawler does not send POST payloads. | Check forms, search, detail pages, and the server routes behind them. |
| ADS-CRAWL-04 | High | Avoid excessive or fragile redirects on pages where ads will show. | Trace redirect chains and cookie / session dependencies. |
| ADS-CRAWL-05 | Medium | Prefer stable, simple URLs over per-user session IDs or one-off dynamic paths for the same content. | Inspect URLs for session / user identifiers; check canonical tags. |
| ADS-CRAWL-06 | High | DNS and hosting must resolve and respond reliably. | Check DNS, TLS, uptime, and server response times. |
| ADS-CRAWL-07 | Medium | New pages may take time to be crawled; large UGC / news / catalog sites should expose stable index paths and a sitemap. | Check the sitemap and internal linking. |

## F. AdSense Program policy requirements

| ID | Severity | Requirement | Check |
| --- | --- | --- | --- |
| ADS-PROG-01 | Blocker | Do not click your own ads, and do not inflate impressions or clicks with bots, repeated manual actions, automated tools, or fraudulent software. | Ask the owner; inspect traffic / automation if data is available. |
| ADS-PROG-02 | Blocker | Do not ask users to click or view ads, offer rewards for ad actions, use phrases like "support us by clicking the ads", or place arrows / images that point at ads. | Inspect the copy near every ad slot and the CTA wording. |
| ADS-PROG-03 | Blocker | Do not make ads hard to tell apart from content, and do not label ads misleadingly. Neutral labels such as "Advertisement" or "Sponsored" are acceptable. | Inspect ad-slot labels and design. |
| ADS-PROG-04 | High | Traffic must come from legitimate sources — no paid-to-click, paid-to-surf, auto-surf, click exchanges, spam email, spam posts, toolbar / software-driven traffic, or online ads with poor landing pages. | Ask the owner; inspect campaign sources if available. |
| ADS-PROG-05 | High | Ad code changes must not inflate performance or harm advertisers. | Inspect any ad code and wrappers present. |
| ADS-PROG-06 | Blocker | Do not place Google ads in software, toolbars, pop-ups / pop-unders, emails, private-message screens, non-content pages, ad-only pages, framed third-party content, or pages that impersonate Google. | Inspect the placement plan and templates. |
| ADS-PROG-07 | High | WebView monetization has separate requirements; a normal website should not assume app / WebView eligibility. | Mark applicable only for an app / WebView audit. |

## G. Google Publisher Policies — prohibited content and conduct

Any matching item is normally a `Blocker` for approval, or for ad serving on the affected pages.

| ID | Requirement | Check |
| --- | --- | --- |
| ADS-PUB-01 | No illegal content, promotion of illegal activity, or violation of others' legal rights. | Review the topic, products, downloads, and instructions. |
| ADS-PUB-02 | No copyright infringement, counterfeit goods, or brand / trademark abuse. | Check copied media, product pages, logo use, and fake brand claims. |
| ADS-PUB-03 | No dangerous or derogatory content: hate, discrimination, harassment, threats, promotion of self-harm, praise of violence, support for terrorist / criminal organizations, extortion. | Review the content and the UGC. |
| ADS-PUB-04 | No promotion of animal cruelty, or sale of products from endangered / threatened species. | Review the niche and product content. |
| ADS-PUB-05 | No misleading representation: do not hide or misstate the publisher's identity, the content creator, the purpose of the content, the content itself, or an affiliation / endorsement / brand relationship. | Check About, author info, branding, logos, product claims, and disclosures. |
| ADS-PUB-06 | No deceptive behavior: phishing, theft of personal information, fake "get rich quick" claims, or intentionally misleading content or service promotion. | Check forms, offers, and lead flows. |
| ADS-PUB-07 | No content that enables dishonest behavior: fake documents, academic cheating, drug-test evasion, hacking / cracking, or unauthorized tracking / spyware. | Review tools, downloads, and tutorials. |
| ADS-PUB-08 | No paid sexual acts, mail-order-bride / international-marriage-broker content, adult themes in family-oriented content, or any child sexual abuse or exploitation material. | Review adult / family / UGC areas carefully. |
| ADS-PUB-09 | Publisher information and ad-request data must be accurate and complete, including the site / app identity and `ads.txt` / `app-ads.txt` where applicable. | Check metadata, the account-to-site mapping, and `ads.txt`. |
| ADS-PUB-10 | Ads must not interfere with content or interaction, overlap navigation, push content down, or trap users on screens that require an ad click to exit. | Inspect the ad-layout plan. |
| ADS-PUB-11 | Do not show ads on screens with no publisher content, low-value content, under-construction content, copied content without added value, an unsupported language, or where paid promotion exceeds the content. | Inspect representative templates. |
| ADS-PUB-12 | Do not place ads out of context: on background pages, off-screen, or on screens where the user's attention is clearly elsewhere. | Inspect the responsive layout and lazy-loaded slots. |
| ADS-PUB-13 | No demonstrably false claims that undermine trust in an election or democratic process, no harmful health claims that contradict scientific consensus, and no climate claims that contradict authoritative scientific consensus. | Review news, health, politics, science, climate, and UGC content. |
| ADS-PUB-14 | No manipulated media that deceives users about politics, social issues, or matters of public concern. | Review images, video, and audio, plus any AI-generated-media disclosure. |
| ADS-PUB-15 | No child endangerment, grooming, sextortion, sexualization of minors, child trafficking, or CSAM. Treat any signal as an immediate hard blocker. | Review content, images, comments, uploads, and moderation logs where available. |
| ADS-PUB-16 | Do not monetize content in a way that exploits, denies, or is insensitive toward an active crisis or an unexpected sensitive event. | Check any news / crisis pages and their monetization context. |

## H. Google Publisher Restrictions — restricted-inventory risk

Restricted content is not always an account or application blocker by itself, but it can sharply
reduce or remove ad demand. Treat as `High` for readiness unless it is isolated and clearly
excluded from ads.

| ID | Requirement | Check |
| --- | --- | --- |
| ADS-REST-01 | Sexual content, sexual entertainment, sexual products, sexual-health supplements, or sexual advice. | Review categories, images, and UGC. |
| ADS-REST-02 | Shocking, graphic, violent, or disgusting content, or prominent obscene language. | Review images, articles, and comments. |
| ADS-REST-03 | Explosives, firearms, firearm parts, other weapons, or instructions to obtain / assemble / improve them. | Review products and tutorials. |
| ADS-REST-04 | Tobacco, recreational drugs, drug paraphernalia, or instructions for drug production / use. | Review products and articles. |
| ADS-REST-05 | Online alcohol sales, or promotion of irresponsible drinking. | Review ecommerce / affiliate links and the framing. |
| ADS-REST-06 | Online gambling or paid games of chance, subject to location exceptions. | Review offers and target geographies. |
| ADS-REST-07 | Prescription-drug sales, online pharmacies, unapproved drugs / supplements, or delisted Google Play apps. | Review health / ecommerce / app content. |
| ADS-REST-08 | Ad obstruction: ads covering content, content covering ads, hidden video-ad controls, unsupported video implementations, or autoplay / sticky-video violations. | Inspect the layout and any video placements. |

## I. Privacy and data requirements

| ID | Severity | Requirement | Check |
| --- | --- | --- | --- |
| ADS-PRIV-01 | Blocker | Publish and follow a privacy policy that discloses the data collection, sharing, and use caused by Google's products, including cookies, web beacons, IP addresses, and other identifiers. | Inspect the privacy page and the footer link. |
| ADS-PRIV-02 | High | Disclose that third parties may set or read cookies, or use web beacons / IP addresses, because ads are served on the site. | Check the privacy-policy wording. |
| ADS-PRIV-03 | High | Do not pass personally identifiable information to Google in ad requests, and do not use Google services to identify users without the required notice / consent. | Inspect URLs, query parameters, the ad code, and the analytics / ad-personalization setup. |
| ADS-PRIV-04 | High | Comply with Google's EU user consent policy where applicable (a Google-certified CMP for EEA / UK traffic). | Check the consent banner / CMP for EEA / UK visitors. |
| ADS-PRIV-05 | High | If precise location data is collected, disclose the use, obtain opt-in consent, transmit it securely, and document it in the privacy policy. | Check site / app permissions and data flows. |
| ADS-PRIV-06 | High | If content is child-directed or COPPA-covered, mark it appropriately and do not use interest-based targeting for children. | Check the audience, the content, and the account settings. |
| ADS-PRIV-07 | High | Do not set, modify, intercept, or delete cookies on Google domains. | Inspect scripts only if custom ad / proxy code exists. |
| ADS-PRIV-08 | High | Do not use Google ad code or platform products to target personalized ads, or build audience lists, from child-directed activity, adult / gambling / government-site activity, or sensitive information (health, financial hardship, ethnicity, religion, crime, political affiliation, union membership, sexual behavior, or sexual orientation). | Inspect ad personalization, remarketing, audience lists, analytics audiences, and data-layer events. |
| ADS-PRIV-09 | High | In the US and Canada, do not target housing, employment, or credit-related ads by gender, age, parental status, marital status, or postal code. | Check the ad / marketing audience settings if the site advertises or retargets these categories. |
| ADS-PRIV-10 | Medium | If personalized ads are used, confirm the publisher has the rights to the audience data and shows the required interest-based-advertising disclosures or controls. | Check the consent / CMP, the privacy policy, and any ad-choices disclosure. |

## J. Recommended audit output

```markdown
**Decision**
Not ready / Ready after fixes / Ready   — one-line reason.
This is an assessment, not a guarantee of approval.

**Blockers**
- `ADS-CONTENT-02`: Issue. Evidence. Basis. Fix.

**High risks**
- `ADS-CRAWL-02`: Issue. Evidence. Basis. Fix.

**Medium risks**
- `ADS-UX-05`: Issue. Evidence. Basis. Fix.

**Exhaustive checklist**
Every requirement ID in this reference appears exactly once.

| ID | Status | Severity | Evidence | Next action |
| --- | --- | --- | --- | --- |
| ADS-ELIG-01 | Pass/Fail/Unknown/N/A | Blocker | ... | ... |
| ADS-ELIG-02 | Pass/Fail/Unknown/N/A | Blocker | ... | ... |
| ... | ... | ... | ... | ... |

**Completeness check**
- Requirement IDs in reference: 73
- Requirement IDs in report: <count>
- Missing IDs: none  (or list them)
```

Rules:
- Do not collapse multiple IDs into one row.
- Do not omit an ID because it seems unlikely — mark it `N/A` with a reason.
- Do not mark an item `Pass` without evidence.
- Use `Unknown` when account data, analytics, AdSense dashboard access, owner confirmation, or
  server access is required and unavailable.

---

## ID index (for the completeness gate — 73 total)

A: ADS-ELIG-01, ADS-ELIG-02, ADS-ELIG-03, ADS-ELIG-04
B: ADS-OWN-01, ADS-OWN-02, ADS-OWN-03, ADS-SITE-01, ADS-SITE-02, ADS-TXT-01, ADS-TXT-02
C: ADS-CONTENT-01, ADS-CONTENT-02, ADS-CONTENT-03, ADS-CONTENT-04, ADS-CONTENT-05, ADS-CONTENT-06, ADS-CONTENT-07, ADS-CONTENT-08
D: ADS-UX-01, ADS-UX-02, ADS-UX-03, ADS-UX-04, ADS-UX-05, ADS-UX-06
E: ADS-CRAWL-01, ADS-CRAWL-02, ADS-CRAWL-03, ADS-CRAWL-04, ADS-CRAWL-05, ADS-CRAWL-06, ADS-CRAWL-07
F: ADS-PROG-01, ADS-PROG-02, ADS-PROG-03, ADS-PROG-04, ADS-PROG-05, ADS-PROG-06, ADS-PROG-07
G: ADS-PUB-01 … ADS-PUB-16
H: ADS-REST-01 … ADS-REST-08
I: ADS-PRIV-01 … ADS-PRIV-10
