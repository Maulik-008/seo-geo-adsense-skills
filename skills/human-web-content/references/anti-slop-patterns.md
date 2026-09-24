# Anti-slop pattern catalogue

Full reference for §9 of the skill. Each entry names the pattern, explains why it reads as machine-written, and shows the fix.

The underlying reason nearly all of these fail: they perform the *shape* of insight without carrying information. A reader gets the feeling of having learned something and none of the substance. Strip the pattern and either a real point appears or nothing does. If nothing does, delete the sentence.

---

## Part 1: Vocabulary

### 1.1 Inflated verbs

| Avoid | Use |
|---|---|
| leverage, utilize, harness | use |
| facilitate, enable | let, help, allow |
| foster, cultivate | build, encourage, grow |
| empower | let, allow, give |
| streamline, optimize | simplify, speed up, cut steps from |
| delve into, explore | look at, examine, cover |
| embark on | start |
| elevate, unlock, supercharge, revolutionize | say what actually changes |
| showcase, highlight, underscore | show, or state the fact |

Each of these has an ordinary word that means the same thing with less fog. Use it unless the inflated word is genuinely the precise one.

### 1.2 Inflated adjectives

robust, seamless, cutting-edge, comprehensive, transformative, pivotal, crucial, vital, paramount, multifaceted, meticulous, intricate, holistic, dynamic, innovative, groundbreaking, remarkable, stunning, vibrant, nestled, renowned, profound.

The problem is not that these words are forbidden. It is that they assert quality instead of demonstrating it. "A robust API" tells the reader nothing. "The API retries failed writes three times and returns the original error on the fourth" tells them what robust means here.

Some are fine in their technical home: "robust" in statistics, "comprehensive" for an index that genuinely covers everything, "dynamic" in programming.

### 1.3 Buzzword phrases

game-changer, paradigm shift, deep dive, actionable insights, best practices, thought leadership, value proposition, digital transformation, move the needle, circle back, synergy, ecosystem (outside biology and software platforms), future-proof, ever-evolving, at scale (as decoration), a testament to.

### 1.4 Empty adverbs

just, literally, simply, actually, truly, honestly, fundamentally, importantly, crucially, inherently, inevitably, notably, arguably.

Cut when they add nothing. Keep when they carry real emphasis, contrast, or uncertainty. "It literally doubled" is fine if it literally doubled. "It's literally the best tool" is noise.

---

## Part 2: Phrases that delay the point

Every one of these is a sentence that has not started yet.

- it is important to note that
- it is worth noting that
- it goes without saying
- needless to say
- in today's fast-paced world / in today's digital age / in the modern era
- in the age of / in the world of / in the realm of
- when it comes to
- at the end of the day
- at its core
- the truth is / the reality is
- in order to (use "to")
- due to the fact that (use "because")
- at this point in time (use "now")
- has the ability to (use "can")
- in this article, we will explore
- let's dive in / let's break this down / let's explore
- here's what you need to know
- without further ado
- now more than ever

**Before:** "It is important to note that, when it comes to invoicing software, in order to get paid faster you need automated reminders."
**After:** "Automated reminders are the feature that actually shortens payment time."

---

## Part 3: Structural patterns

### 3.1 Binary contrast

"It's not X. It's Y." / "The question isn't X, it's Y." / "This isn't just X, it's Y."

Feels like a sharp distinction. Usually is not one. It also smuggles in a claim about X that is never defended.

**Before:** "The question isn't which model you use. It's how you evaluate it."
**After:** "Evaluation matters more than model choice here, because all three models score within two points on this task."

Note the fix does not just flip the sentence. It adds the reason, which is what was missing.

### 3.2 Faux-insight setup

"What most people get wrong," "here's what nobody tells you," "the part everyone misses," "this is the step most guides skip."

These flatter the writer and pad the sentence. The claim underneath is usually ordinary.

**Before:** "Here's what nobody tells you about GST filing: the late fee applies per return, not per month."
**After:** "The late fee applies per return, not per month. Filing GSTR-1 and GSTR-3B late in the same month means two fees, not one."

### 3.3 Colon reveal

A noun phrase, a colon, then a dramatic fragment.

**Before:** "The detail that makes it work: a second model grades the output."
**After:** "It works because a second model grades the output."

Colons are for lists, labels, definitions, and quotations. Not drama.

### 3.4 Fake-depth trailing clauses

Sentences that end with an "-ing" phrase pretending to explain significance: marking, highlighting, underscoring, showcasing, reflecting, symbolizing, signalling, cementing, contributing to.

**Before:** "The company launched the feature in March, marking a pivotal moment in its evolution and reflecting broader industry trends toward automation."
**After:** "The company launched the feature in March. It was the first paid add-on the company had shipped."

### 3.5 Importance puffery

"Stands as a testament to," "plays a vital role in," "solidifies its position as," "underscores the significance of," "marks a turning point," "represents a major step forward."

State the fact. Let the reader decide it is important.

**Before:** "This update marks a pivotal moment in cloud storage."
**After:** "This update added offline access and automatic versioning."

### 3.6 Interpretive metadiscourse

Lines that step outside the subject to tell the reader how to read: "that last point matters more than it sounds," "as you can see," "the key takeaway here is," "this distinction is important," and redundant "in other words."

If the point is clear, cut the aside. If it is not clear, the fix is more support, not more instruction.

### 3.7 Weasel attribution

"Experts agree," "studies show," "research suggests," "many argue," "it is widely regarded as," "industry observers note."

Name the source and link it, or cut the claim. Never invent a source to satisfy this rule.

### 3.8 Rule of three

Forced triplets: "fast, reliable, and powerful." "Innovation, inspiration, and insight." Three feels complete, so the pattern gets used whether or not there are three real items.

Keep the one that is true and support it. If there really are three, list three.

### 3.9 False ranges

"From beginners to experts," "from small startups to large enterprises," "from the early days to the modern era."

These sound inclusive and specify nothing. Name the actual audience or the actual period.

### 3.10 Synonym cycling

Rotating terms to avoid repetition: "the tool... the platform... the solution... the software." The reader now has to check whether these are the same thing.

Pick the right word and repeat it.

### 3.11 Negative listing

"Not a framework. Not a library. A runtime." Just say what it is.

### 3.12 Dramatic fragmentation

"That's it. That's the whole feature." / "One line. That's all it takes." Occasionally effective. Almost never twice in one piece.

### 3.13 Rhetorical setups

"What if I told you," "Think about it:", "Plot twist:", "Sound familiar?", and self-answered questions ("So what does this mean? It means...").

Drop the setup and make the point.

### 3.14 Fake-profound kicker

The final "deep" line: a metaphor, an aphorism, a mic-drop.

Delete it. Do not rewrite it into a better metaphor and do not preserve the rhythm. End on the clearest concrete sentence already in the draft, or add a plain takeaway or next step.

### 3.15 Recap ending

"In conclusion," "Ultimately," "Overall," "To summarize," or a closing paragraph restating the article.

The reader just read it. End on the last useful thing.

### 3.16 Copula avoidance

Elaborate substitutes for "is" and "has": "serves as," "functions as," "stands as," "acts as," "represents," "boasts," "features."

**Before:** "The app serves as a centralized hub for expense management."
**After:** "The app tracks receipts, categorizes spending, and exports to Tally."

### 3.17 Uniform paragraphing

Every paragraph the same visual size. Real writing varies because ideas need different amounts of room. The opposite failure, every paragraph one line, is equally mechanical.

### 3.18 Repetitive sentence openings

Five consecutive sentences starting with "This," or "The," or a participle. Scan the first two words of each sentence in a paragraph. If they repeat, restructure.

### 3.19 Overexplaining the obvious

Defining terms the audience already knows, restating a point three ways, or explaining why a step is necessary when it is self-evident. Trust the reader.

### 3.20 Template sections

"Challenges and Future Outlook," "Benefits and Drawbacks," "Final Thoughts," "Key Takeaways" appearing on every article regardless of topic. If a section is present because the template says so rather than because it carries content, delete it.

---

## Part 4: Formatting

- **Bold mid-sentence** for emphasis, scattered through paragraphs. Reserve bold for genuinely critical warnings. One or two per article.
- **Emoji in headings.** No.
- **Bullets replacing prose.** Lists are for genuinely parallel items the reader will scan or compare. Two connected sentences should be two sentences.
- **Headings over tiny sections.** If a section is two sentences, fold it into its neighbour.
- **Tables padded with "N/A" or "Varies."** If a column has no real content, drop the column.
- **Nested bullets three levels deep.** Restructure instead.

---

## Part 5: Em dashes

Not banned. Overused by AI models as a default rhythm device, which is why they cluster.

Rules:
- Short copy (product page, meta description, social, under 300 words): none.
- Long article: at most one or two, only where the dash clearly beats a comma, a full stop, or brackets.
- Never two in a paragraph.
- Never a pair of dashes framing an aside when brackets or a separate sentence would do.

If a draft has six of them, the problem is sentence construction. Restructure the sentences rather than swapping punctuation.

---

## Part 6: What NOT to do in the name of sounding human

This section exists because the common "humanizing" advice is often worse than the disease.

**Do not add deliberate grammatical errors.** Errors do not signal humanity, they signal carelessness, and on a site trying to establish trust they cost more than they gain.

**Do not invent personal anecdotes.** "When I tested this last month" about an untested product is a fabrication. It is also easy to catch and impossible to defend.

**Do not vary sentence length randomly.** Variation that does not track the ideas reads as jittery rather than natural. Length should follow content.

**Do not sprinkle filler as voice markers.** "Basically," "honestly," "actually," "I mean" inserted at intervals is a tic, not a personality.

**Do not perform casualness.** Forced informality on a technical reference page reads worse than plain neutral prose.

**Do not chase detector scores.** Detectors are unreliable in both directions and optimizing against them degrades the writing. The goal is content someone would want to read, and that goal is reached by writing better, not by writing differently.

**Do not confuse "sounds human" with "is useful."** A page can be perfectly natural in voice and completely empty. Voice is the last layer, not the first.

---

# Part 7: False-positive prevention

The lists in this file are search aids, not bans. Flagging a word without reading the sentence produces worse writing, not better. Three rules keep the scan honest.

## 7.1 Exclusion zones

Never flag text inside:

- Direct quotations from a cited source. The words belong to the source and must not be altered.
- Titles, product names, statute names, and other verbatim values.
- Code, configuration, or markup shown as an example.
- A passage that is naming or critiquing the pattern itself.

## 7.2 Context-aware severity

A watched word sitting next to specific named entities, dates, statute numbers, or amounts is probably being used with technical meaning rather than as filler. Lower the flag.

- Higher severity: "a comprehensive examination of the issues": abstract nouns, no specifics.
- Lower severity: "the comprehensive audit the FTC ran in 2024": named actor, named year.

## 7.3 Metaphorical versus literal

These need the surrounding words checked. Only the figurative use is a defect.

| Word | Fine | Flag |
|---|---|---|
| ecosystem | the Android app ecosystem | the repair ecosystem |
| landscape | the Rajasthan landscape | the regulatory landscape |
| navigate | navigate the settings menu | navigate the approval process |
| robust | a robust estimator (statistics) | a robust approach |
| tapestry | a medieval tapestry | a tapestry of regulations |
| beacon | a lighthouse beacon | a beacon of innovation |
| testament | last will and testament | a testament to quality |
| architecture | the building's architecture | the architecture of the argument |

## 7.4 On numeric thresholds

Published anti-AI guides circulate specific numbers: paragraph word counts within 15% of each other, no sentence under 8 or over 30 words per 500-word block, more than 30% of paragraphs opening with a transition, segmental entropy variance under 10%.

Treat these as places to look, never as targets to hit. Writing toward a variance number produces prose shaped by arithmetic rather than by meaning, which is the original problem wearing a different mask. Open the paragraph the number points at and read it. Decide with your eyes.

The same applies to model-fingerprint lists that claim particular models favour particular opening words. These change with every release, they flag ordinary human sentences constantly, and writing to avoid them is detector-chasing.

## 7.5 Hallucinated markup

Search every draft for these strings before publishing. They are artifacts leaked from model tooling and their presence in a live page is unambiguous:

`oaicite`, `contentReference`, `turn0search`, `turn0news`, `grok_card`, `citeturn`, `:contentReference[oaicite:`

Also check for stray citation brackets with no source, duplicated reference markers, and half-rendered markdown in plain-text contexts.
