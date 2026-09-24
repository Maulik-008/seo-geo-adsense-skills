# Content-type playbooks

Detailed rules per content type. Reference for §11 of the skill.

Each playbook lists what the type must contain, the structure that usually fits, and the specific way this type tends to fail.

---

## How-to and tutorials

**Must contain**
- Prerequisites, stated before step one: accounts, tools, versions, permissions, cost.
- A realistic time estimate.
- Numbered steps in the order they are performed.
- For each step, what the reader should see or have afterwards. Without this they cannot tell whether it worked.
- The likely failure at each step, placed at that step.
- The end state, described concretely.

**Structure**
Prerequisites, time, steps, verification, common failures that are not step-specific, next step.

**How it fails**
- Steps that skip an assumption the writer forgot they were making.
- No way to verify progress, so the reader discovers at step 9 that step 3 failed.
- A troubleshooting section at the end instead of warnings where they are needed.
- Screenshots described but not supplied. If the user has none, write the steps so they work without images.
- Version drift. Say which version the steps were written against.

---

## Comparisons

**Must contain**
- The criteria that actually decide the choice, established before any feature list.
- Honest treatment of what each option is bad at.
- A recommendation per reader type, not a single winner.
- Real pricing, dated.
- Where the options are genuinely equivalent, say so instead of manufacturing distinctions.

**Structure**
What the choice depends on, criteria one by one across all options, then recommendations by reader type.

**How it fails**
- Feature-table comparisons where the table settles nothing because no criterion is weighted.
- One option winning every row, which means the piece is an advertisement.
- Comparing options that are not actually alternatives for the same job.
- Omitting the free or manual option when it is a legitimate answer.

---

## Reviews

**Must contain**
- The basis, stated plainly and early. "I used this for six months," "I ran it for a week," and "this is based on the documentation and user reports" are three different claims with three different weights. Never blur them.
- What it does badly. A review without a negative is not a review.
- Who should not buy it.
- Price, plan limits, and the date checked.

**How it fails**
- Implied testing that did not happen. This is the single most damaging thing in this category.
- Complaints so mild they read as marketing ("the only downside is that it does so much").
- Affiliate incentives shaping the verdict without disclosure.

---

## Explainers

**Must contain**
- A plain definition in the first paragraph, in words the target reader already has.
- Why the thing exists, meaning what problem it solved.
- How it works, at a depth matched to the reader.
- One concrete example.
- Where readers commonly go wrong.

**Structure**
Definition, why it exists, how it works, example, common confusion, where to go deeper.

**How it fails**
- Defining a term with three other undefined terms.
- Analogies that break under any weight. If you use one, say where it stops being true.
- Encyclopedic completeness in place of understanding. The reader wanted to understand it, not to read everything about it.

---

## Listicles

**Must contain**
- A distinct reason for each entry to exist. If two entries make the same point, merge them.
- Entries ordered by something real: importance, sequence, or use case. Not arbitrarily.
- A stated basis for selection.

**How it fails**
- Padding to hit the number in the title. If only six entries earn a place, change the title to six.
- Entries with identical structure and length, which makes the whole page read as generated.
- "Best X" lists that are just the vendors with affiliate programs.

---

## News and updates

**Must contain**
- What changed, precisely.
- Who is affected, and who is not.
- What they need to do, and by when.
- The effective date and the publication date.
- A link to the primary announcement.

**How it fails**
- Rewriting a press release without adding interpretation.
- Speculation presented as fact, especially about unannounced dates and prices.
- No date on the page, so a reader six months later cannot tell if it still applies.

---

## Landing and product pages

**Must contain**
- What the product does, in one concrete sentence.
- Who it is for, and who it is not for.
- Real pricing, or a plain explanation of why pricing is not listed.
- Claims a reader could verify.

**How it fails**
- Adjective stacks in place of capability.
- Superlatives with no basis.
- Hiding pricing behind a form when competitors publish theirs.
- Testimonials with no attribution.

Naming who the product is not for builds more trust than any superlative. It is also unusual enough that readers notice.

---

## FAQs

**Must contain**
- Questions people genuinely ask, drawn from support tickets, search queries, sales calls, or forum threads.
- The answer in the first sentence, then the qualification.
- Short answers. If one needs 800 words, it is an article, not an FAQ entry.

**How it fails**
- Invented questions phrased as keywords ("What are the best invoicing tools in India 2026?").
- FAQ sections bolted on for schema markup rather than for readers.
- Answers that restate the article above.

---

## Reference and documentation pages

**Must contain**
- Predictable, consistent organization.
- Accuracy above readability, where the two conflict.
- Complete coverage of the parameter, field, or rule set.
- Version and date.

**How it fails**
- Prose where a table is correct.
- Inconsistent naming across entries.
- Silent omissions, which are worse here than anywhere else because readers assume completeness.

---

## Personal or opinion pieces

**Must contain**
- An actual position.
- The reasoning behind it.
- Honest acknowledgment of the strongest counter-argument.
- Specifics from real experience, if the writer has it.

**How it fails**
- Balanced to the point of saying nothing.
- Opinion with no supporting detail, which is just assertion.
- Manufactured contrarianism.

---

## Category and hub pages

**Must contain**
- A real explanation of what the category covers and how it is organized.
- Enough context that the page is useful on its own, not just a link list.

**How it fails**
- A paragraph of keyword text above a list of links, which is one of the clearest thin-content patterns there is.

---

## Multiple articles for one site

When producing a set:

- Vary the structures deliberately. Not every piece is a numbered guide.
- Vary the opening approach. Not every piece opens with the problem statement.
- Vary the length according to what each topic needs.
- Do not reuse the same phrases, transitions, or closing move across pieces.
- Cross-link where a link genuinely helps, not to build an internal link count.
- Keep the topic set coherent. A site covering one subject well is worth more than a site covering ten subjects thinly, both to readers and to Google's site-level assessment.
