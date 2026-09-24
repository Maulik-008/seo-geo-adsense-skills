# Playbook: Claim Check

## Purpose

Prevent generated pages from publishing unsupported claims, especially on alternative/comparison pages.

## Inputs

- Page brief/spec.
- `PAGEWELL.md` product facts and supported/prohibited claims.
- Competitor/alternative facts supplied by user or verified sources.
- Generated page copy.

## Claim categories

### Safe claims

- Claims present in `PAGEWELL.md` product facts or supported claims.
- Claims directly provided by the user in the brief.
- Claims visible in current site/product copy.
- Generic, non-comparative statements that do not imply unverifiable facts.

### Risky claims

- "Best", "fastest", "#1", "most accurate".
- Competitor weaknesses.
- Pricing comparisons.
- Customer counts.
- Revenue, conversion, traffic, or performance metrics.
- Security/compliance claims.
- Integration support not present in `PAGEWELL.md` product facts or supported claims.

### Disallowed claims unless sourced

- Fake reviews/testimonials.
- Fake ratings.
- Fake customers/logos.
- Claims about competitor internal behavior or roadmap.
- Legal/security/compliance claims without source.

## Process

1. List each concrete claim in the page.
2. Mark each claim as:
   - supported
   - provided by brief
   - generic/low-risk
   - unsupported
3. Rewrite or remove unsupported claims.
4. For comparisons, prefer:
   - "When to choose X"
   - "When to choose Y"
   - "X is designed for..."
   - "Y may be a fit when..."

## Output

```md
# Claim Check: <route>

Status: PASS | FAIL

## Supported claims
- ...

## Rewritten/removed claims
- ...

## Remaining risks
- ...
```

## Acceptance criteria

- No unsupported high-risk claims remain.
- Alternative/comparison pages are factual and fair.
