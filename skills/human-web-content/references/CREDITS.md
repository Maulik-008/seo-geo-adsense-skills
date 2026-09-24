# Credits and sources

## Primary sources

- Google Search Central, "Creating helpful, reliable, people-first content" (updated 10 December 2025): the self-assessment questions, E-E-A-T framing, and the Who/How/Why model in §10 and `quality-standards.md`.
- Google Search Central Blog, "What web creators should know about our March 2024 core update and new spam policies": the definitions of scaled content abuse, expired domain abuse, and site reputation abuse quoted in §10.0.
- Google Search Central, Spam Policies for Google Web Search: ongoing policy text.

Google's guidance is revised periodically. Verify against the live pages before relying on any specific wording.

## Open-source writing skills studied

Ideas from these were adapted, not copied. Each is independently installable if you want the original.

**Clarity**, Addy Osmani (MIT). https://github.com/addyosmani/clarity
The flatten and relation tests, the `[TK]` gap convention, and medium routing. Those three live in the separate `clarity-pass` skill rather than here.

**no-ai-slop**, Peter Yang (MIT). https://github.com/petergyang/no-ai-slop
The portability test, minimum-effective-edit discipline, and much of the pattern vocabulary in `anti-slop-patterns.md`. This is the same skill distributed as the `anti-ai-slop-content-writer` plugin.

**no_ai_slop_writing_rules**, Rossmann Group. https://github.com/realrossmanngroup/no_ai_slop_writing_rules
Root-cause differentiation (§2), the defamation framing on fabricated attributions and the quote-accuracy rule (§6), the ban on research-process narration (§6), heading anti-patterns (§4.6), and the false-positive prevention approach in `anti-slop-patterns.md` Part 7.

**anti-ai-writing-style-avikbal**, Avik Bal (MIT). https://github.com/avikbal-dm/anti-ai-writing-claude-skill
The full reframe catalogue and the analogy permission test in `reframe-and-metaphor.md`, and the anti-overfitting framing in §9.7.

**anti-ai-slop-writing**, jalaalrd. https://github.com/jalaalrd/anti-ai-slop-writing
The parataxis warning in §4.4, which is the one place most anti-slop advice actively makes writing worse.

## Deliberately not adopted

Recorded so the decisions are not silently reversed later.

- **Model-specific opening-word lists** (jalaalrd). Which words a given model favours changes every release, the lists flag ordinary human sentences constantly, and writing to avoid them is detector-chasing.
- **Numeric stylometric targets** (Rossmann's detection reference): paragraph variance under 15%, no sentence under 8 or over 30 words per 500 words, segmental entropy thresholds. Kept as diagnostics in Part 7, rejected as targets. Clarity's own lint script refuses to emit a composite score for this reason: when they tested one, the genuinely human control text scored as the riskiest.
- **Blanket ban on passive voice** (jalaalrd). Wrong for documentation, academic, and legal prose, where the actor is often unknown or irrelevant.
- **Absolute em-dash ban** (Rossmann rule 1, jalaalrd). This skill allows one or two in long copy where they clearly beat the alternatives. The defect is the cluster, not the character.
- **"Include friction, doubt, or mess"** and **"let sentences be ugly"** (jalaalrd). Sound advice for a writer describing their own experience, dangerous as an instruction to a model, which will manufacture the friction. §9.7 bans exactly this.
- **"Run it through an AI humanizer"** (widely repeated in AdSense advice). Changes surface statistics without adding information, and can corrupt text that was correct.
- **Blanket ban on all analogies** (avikbal's default). Adopted as a strong default with a budget, but explainers for beginners keep one, because that is where an analogy genuinely does work prose cannot.
