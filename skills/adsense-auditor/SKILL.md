---
name: adsense-auditor
description: Audit websites for Google AdSense application readiness and ad-serving compliance. Use when checking whether a site is likely to satisfy AdSense eligibility, site ownership, content quality, navigation, crawler access, ads.txt, privacy disclosure, Google Publisher Policies, AdSense Program policies, or when the user asks if a site can apply for AdSense, pass AdSense review, show ads, or fix an AdSense rejection / "site not ready" / "low value content" issue.
---

# AdSense Site Auditor

## Core rule

Use Google AdSense and Google Publisher official documentation as the source of truth. This skill
turns those docs into an actionable website audit. **It cannot guarantee approval.** No writing
method or checklist can. Say this to the user once, then run the audit.

Before a serious audit, refresh the official docs when internet access is available, because
AdSense policies change. If the live docs conflict with this skill, **the live Google docs win**
— note the conflict in the report.

Every audit must explicitly evaluate **every** checklist item in
`references/adsense-requirements.md`. Do not sample, summarize, or check only the likely problem
areas. For each requirement ID, assign exactly one status: `Pass`, `Fail`, `Unknown`, or `N/A`.
Use `N/A` only when the requirement genuinely does not apply to the site type or monetization
mode, and state why.

## Required reference

Read `references/adsense-requirements.md` before auditing. It holds the full checklist (73 IDs),
severity mapping, and the official English source URLs.

## Audit workflow

### 1. Identify the target
- Live URL / domain, repository path, or both.
- Whether the audit is **pre-application**, **post-rejection**, or **ad-serving cleanup**.
- Site type: normal website, CMS / blog, directory, ecommerce, tool / app, UGC site, video site,
  or login-gated product. (Type changes which IDs are `N/A`.)

### 2. Gather evidence
- Crawl the homepage and a representative set of content pages (not just the homepage).
- Check `robots.txt`, XML sitemap, canonical URLs, redirects, HTTP status codes, login walls,
  WAF / bot-protection / geoblocking symptoms, and whether important pages render without
  POST-only state.
- Confirm the AdSense crawler user agent (`Mediapartners-Google`) and `AdsBot-Google` are not
  blocked in `robots.txt` or by a firewall.
- Inspect the privacy policy, About / Contact / ownership signals, navigation, content depth,
  ad / affiliate density, copied or embed-only content, and any prohibited / restricted content
  risk.
- If repository access exists, inspect templates / routes / content sources — not only the
  rendered homepage.
- For a real account audit, check the AdSense **Sites** page status if it is accessible
  (`Getting ready` / `Ready` / `Needs attention` / `Not ready` and the stated policy issue).

### 3. Classify findings
- `Blocker` — likely to prevent approval, or a hard policy violation, or the application cannot
  be verified.
- `High` — a meaningful approval or ad-serving risk.
- `Medium` — a quality, crawlability, UX, disclosure, or evidence gap to fix before applying.
- `Pass` — checked, with evidence.
- `Unknown` — cannot verify from the access available; state exactly what is needed.
- `N/A` — not applicable; state the site condition that makes it irrelevant.

### 4. Produce the audit report
- **Executive decision:** `Ready`, `Not ready`, or `Ready after fixes`.
- Findings first, ordered by severity.
- For each finding: requirement ID · the issue · the evidence · the official basis (link) · the
  exact fix.
- End with the **exhaustive checklist table** — every requirement ID from the reference, exactly
  once, with `Pass` / `Fail` / `Unknown` / `N/A`, evidence, and next action.

## Implementation guidance

Prefer concrete checks over generic advice:

- Say "`robots.txt` blocks `Mediapartners-Google`", not "crawler issue".
- Say "article pages are mostly scraped snippets with no added commentary", not "thin content".
- Say "ad and affiliate blocks exceed the main content area above the fold", not "too many ads".
- Say "the privacy policy does not disclose third-party ad cookies or Google's data use", not
  "privacy policy incomplete".

Do not advise applying until **all Blockers are resolved** and every High risk is either fixed or
explicitly accepted by the owner.

## Completeness gate

Before finishing, count the requirement IDs in `references/adsense-requirements.md` and compare
with the IDs in your final checklist. If any ID is missing, the audit is incomplete — add the
missing rows before giving a readiness decision.

## Output format

```markdown
**Decision**
Not ready / Ready after fixes / Ready   — plus a one-line reason.
Note: this is an assessment, not a guarantee of approval.

**Blockers**
- `ADS-CONTENT-02`: <issue>. Evidence: <quote / URL / observation>. Basis: <official link>. Fix: <exact step>.

**High risks**
- `ADS-CRAWL-02`: <issue>. Evidence. Basis. Fix.

**Medium risks**
- `ADS-UX-05`: <issue>. Evidence. Basis. Fix.

**Exhaustive checklist**
Every requirement ID in the reference appears exactly once.

| ID | Status | Severity | Evidence | Next action |
| --- | --- | --- | --- | --- |
| ADS-ELIG-01 | Pass/Fail/Unknown/N/A | Blocker | ... | ... |
| ADS-ELIG-02 | ... | ... | ... | ... |
| ... | ... | ... | ... | ... |

**Completeness check**
- Requirement IDs in reference: <count>
- Requirement IDs in report: <count>
- Missing IDs: none  (or list them)
```

Rules:
- Do not collapse multiple IDs into one row.
- Do not omit an ID because it seems unlikely — mark it `N/A` with a reason.
- Do not mark an item `Pass` without evidence.
- Use `Unknown` when account data, analytics, AdSense dashboard access, owner confirmation, or
  server access is required and not available.

## Related skills

This skill audits. To fix the findings end to end (content triage, trust pages, writing, per-page quality gate, re-audit, rejection recovery), use `adsense-content-pipeline`.

## Attribution

Checklist structure adapted from a public "AdSense Site Auditor" skill template published by
CoworkHow (an independent resource, not affiliated with Anthropic or Google). All policy content
here is re-grounded in Google's own English documentation — see the source URLs in
`references/adsense-requirements.md`. Adapted and installed for this project on 2026-09-09.
