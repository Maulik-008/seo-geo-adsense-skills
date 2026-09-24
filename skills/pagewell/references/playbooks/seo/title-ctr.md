# Playbook: Optimize Page Title

## Purpose

Audit and rewrite page titles for search intent and click-through rate.

This skill is specialized. `qa.md` checks whether titles exist and are unique; this skill improves titles that are technically valid but weak.

## Required inputs

- `PAGEWELL.md`
- page route(s) or page files
- current titles/descriptions
- primary keyword or inferred search intent
- page type
- optional Search Console CTR/impression data

## Core principle

For non-homepage SEO pages, every title character should support the search query or click. Google often displays the site/domain separately, so appending the brand usually wastes space.

## When to keep the brand in the title

Keep brand when:

- it is the homepage
- it is the canonical product/entity page and the product name is the query
- the query itself includes the brand/product name
- legal/compliance/brand requirements demand it

Otherwise, remove brand suffixes like:

- `| Brand`
- `- Brand`
- `Brand |`
- `Brand -`

## Title formulas by page type

### Product pages

```txt
<Product Name> - <Primary Category or Benefit>
```

### Use-case pages

```txt
<Use Case> - <Key Benefit>
```

### Free tool pages

```txt
<Tool Name> - Free <Utility>
```

### FAQ pages

```txt
<Question> - <Short Answer Phrase>
```

### Glossary pages

```txt
<Term> - Definition, Examples & How to Use
```

### Alternative/comparison pages

```txt
<Competitor> vs <Product> - <Year> Comparison
Best <Competitor> Alternatives in <Year>
```

Use “Best” only when the page actually compares multiple alternatives and does not rely on unsupported claims.

## CTR modifiers

Use when truthful and space allows:

- Free
- Online
- Fast
- Instant
- Examples
- Guide
- Tutorial
- Template
- Calculator
- Generator
- Preview
- Current year when the page is maintained

## Process

1. Identify the primary keyword/search intent.
2. Identify page type.
3. Remove brand suffix unless allowed above.
4. Put primary keyword near the front.
5. Add secondary benefit/modifier if useful.
6. Keep title roughly 30-60 characters where practical.
7. Ensure no two indexable pages share the same title.
8. Update metadata using the site's existing convention.
9. If title is based on performance data, record the old and new title for later CTR comparison.

## Output

For audits, return:

```md
# Page Title Optimization

| Route | Current Title | Recommended Title | Reason |
|---|---|---|---|
```

For implementation, update the relevant metadata and report changed files.

## Acceptance criteria

- Titles are unique.
- Non-homepage titles avoid unnecessary brand suffixes.
- Primary keyword/search intent is clear.
- Titles are concise and click-oriented without being misleading.
