# Local Overrides — CORE-EEAT in this skill set

Read before scoring. These rules sit on top of the upstream benchmark ([core-eeat-benchmark.md](shared/core-eeat-benchmark.md)). They never change item IDs, weights, vetoes, or the scorer. They govern **which evidence counts** and **what fixes may be recommended**, because several items, read literally, reward behavior that the `human-web-content` and `clarity` skills forbid.

## 1. This skill scores; it does not write

When a finding needs new or rewritten copy, hand the fix to `human-web-content` (web pages) or `clarity` (authored prose). Never recommend adding an element to a page just to pass an item.

## 2. Never fabricate to pass

Items pass only on real, observable evidence:

- Experience (Exp01–Exp09), original data (E01, E03), methodology (R05, Ept05), quantities (R01), citations (R02–R03), credentials (Ept02), reviewer labels (Ept10).
- If the evidence is absent, the state is `fail`, or `unknown` if you cannot observe it. The fix is **"ask the author for their real material"**.
- Never suggest writing "I tested", "after 6 months of use", invented figures, placeholder citations, or a "Reviewed by" line that names no real, qualified reviewer.

## 3. Count thresholds are heuristics

"≥5 numbers", "≥1 citation per 500 words", "≥10 sensory words", "paragraphs 3–5 sentences", "1–2 lists per 500 words", and "bio >30 words" are upstream heuristics, not Google policy. Score them, but never recommend padding a page to meet one.

## 4. Style-conflict items are low severity

For O02 (TL;DR), O06 (paragraph length), O07 (bolding key concepts), C06 ("this article is for…") and C10 (a conclusion that loops back):

- Score normally.
- A failure is at most a **Medium** finding.
- The recommended fix must respect human-web-content §4 and §9: no sprinkled bold, no recap endings, and paragraph length that follows the idea.

## 5. Exp02 (Sensory Details)

The catalog makes Exp02 conditional ("sensory observation is material to the subject"). For software, services, and informational pages, record `na` with that reason. The same applies to the other conditional items (Exp01, Exp04, Exp05, Exp07, Exp09, E01–E05, E10): when the page makes no such claim, the item is `na`. It is not a failure to be "fixed" by adding claims.

## 6. FAQ and schema (C09, O05)

Google now shows FAQ rich results only for authoritative government and health sites, and HowTo rich results are deprecated. FAQPage markup is still valid structured data, but never promise a rich result from it. Never add FAQs that exist only to hold keywords.

## 7. Authority items (A01–A10)

These are site or brand level. From a single page they are often `unknown`, and they cannot be fixed by editing the page. List them separately from page fixes.

## 8. AI-engine preference tables

The per-engine citation preferences in the benchmark are unverified upstream claims. Treat them as hypotheses, and never quote them to a user as measured behavior.

## 9. AdSense and policy items

For T01 (legal pages), T02 (contact), T07 (ad experience), and anything touching AdSense eligibility, the official-docs checklist in `adsense-auditor` is authoritative. When the two disagree, cite the `ADS-*` ID.

## 10. YMYL

For health, finance, legal, and safety content (T08, Ept01, Ept02), apply the stricter bar: dated primary sources, a stated jurisdiction, and a real named reviewer.
