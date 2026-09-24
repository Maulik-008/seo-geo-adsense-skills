# FAQ and Glossary Strategy

FAQ and glossary pages build topical authority by answering narrow questions and defining domain vocabulary.

## FAQ pages

FAQ pages target exact question searches.

Route pattern:

```txt
/faq/<question-slug>
```

Good questions:

- `What is <term>?`
- `How do I <action>?`
- `Can I <action> with <tool>?`
- `How to <action> without <constraint>?`
- `<product> vs <alternative>?`

FAQ coverage:

1. H1 as exact question.
2. First sentence gives direct answer.
3. Short expansion.
4. Example/steps if useful.
5. Related questions/pages.
6. Product/tool CTA if natural.

## Glossary pages

Glossary pages target definition and meaning searches.

Route pattern:

```txt
/glossary/<term-slug>
```

Good terms:

- product category vocabulary
- technical concepts your ICP searches
- feature-adjacent terms
- formats, protocols, workflows, standards

Glossary coverage:

1. H1: `What is <Term>?`
2. One-line definition.
3. Expanded explanation.
4. Example or practical use.
5. Related terms.
6. Related product/use-case/free-tool links.

## Schema

FAQ pages can use `FAQPage` when visible question/answer content matches the JSON-LD.

Glossary pages can use:

- `DefinedTerm`
- `DefinedTermSet`
- `BreadcrumbList`

## Guardrails

- One page per distinct intent.
- No near-duplicate question pages.
- No padding for word count.
- No definitions outside the site's real domain.
- Use internal links to connect related concepts and product workflows.
- Treat coverage lists as intent requirements, not mandatory headings or fixed layouts.
