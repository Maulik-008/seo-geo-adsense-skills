# Agent Flows

How the four agents work, which skills each one uses, and how to run them. The diagrams are Mermaid, so they render as flowcharts on GitHub and in VS Code's Markdown preview.

- [1. The big picture](#1-the-big-picture)
- [2. Which agent do I use?](#2-which-agent-do-i-use)
- [3. adsense-readiness-checker](#3-adsense-readiness-checker)
- [4. content-quality-rewriter](#4-content-quality-rewriter)
- [5. serp-snippet-writer](#5-serp-snippet-writer)
- [6. adsense-content-loop](#6-adsense-content-loop)
- [7. Skills each agent uses](#7-skills-each-agent-uses)
- [8. Rules every agent follows](#8-rules-every-agent-follows)
- [9. Install and run](#9-install-and-run)

---

## 1. The big picture

A typical AdSense push: check the site, fix the existing pages, add new pages, fix the snippets, then check again before applying.

```mermaid
flowchart TD
    START(["Your site"]) --> CHECK["<b>adsense-readiness-checker</b><br/>What is wrong?"]
    CHECK --> DECIDE{"Decision"}
    DECIDE -->|"Ready"| APPLY(["You apply in AdSense"])
    DECIDE -->|"Not ready /<br/>Ready after fixes"| FIXLIST["Fix list:<br/>blockers, weak pages,<br/>missing trust pages"]

    FIXLIST --> REWRITE["<b>content-quality-rewriter</b><br/>Fix existing pages"]
    FIXLIST --> LOOP["<b>adsense-content-loop</b><br/>Create missing pages"]
    FIXLIST --> YOU["<b>You</b><br/>Trust pages, tech fixes,<br/>your real material for TK items"]

    REWRITE --> SNIP["<b>serp-snippet-writer</b><br/>Titles, meta, OG, JSON-LD"]
    LOOP --> REVIEW
    SNIP --> REVIEW["You review and publish"]
    YOU --> REVIEW
    REVIEW --> CHECK

    APPLY --> OUTCOME{"Google's decision"}
    OUTCOME -->|"Approved"| DONE(["Place ads by the placement rules"])
    OUTCOME -->|"Rejected"| CHECK
```

The `adsense-content-pipeline` skill is the rulebook behind all of this. It holds the phases, the publish gate, the rules for which skill wins when they disagree, and the rejection playbook. The agents follow it.

---

## 2. Which agent do I use?

```mermaid
flowchart TD
    Q{"What do you need?"}
    Q -->|"Is my site ready?<br/>Why was I rejected?"| A1["adsense-readiness-checker"]
    Q -->|"I have written content;<br/>check it and fix it"| A2["content-quality-rewriter"]
    Q -->|"Better titles, descriptions,<br/>social tags, schema"| A3["serp-snippet-writer"]
    Q -->|"New articles from scratch,<br/>researched and checked"| A4["adsense-content-loop"]
```

| Agent | Changes files? | Typical run |
|---|---|---|
| `adsense-readiness-checker` | No. Writes one report. | 1 site, up to 20 pages sampled |
| `content-quality-rewriter` | Writes `*.rewritten.md` next to the original; never overwrites | 1–5 pages |
| `serp-snippet-writer` | Writes a snippets report; edits head tags only in `apply` mode | 1–50 pages |
| `adsense-content-loop` | Writes a new folder per topic | 1–5 topics |

---

## 3. adsense-readiness-checker

**Purpose:** a read-only inspection of the whole site, ending with *Ready / Ready after fixes / Not ready*.

```mermaid
flowchart TD
    IN["Input: site URL<br/>optional: stage, rejection message,<br/>repo path, account facts"] --> MAP["1. Map the site<br/>homepage, robots.txt, sitemap,<br/>ads.txt, nav and footer links"]
    MAP --> SAMPLE["2. Pick up to 20 pages<br/>every nav section, newest, oldest,<br/>an archive, all trust pages"]
    SAMPLE --> TECH["3. Technical checks<br/>seo_audit.py, AdSense crawler allowed?,<br/>HTTPS, 404/5xx, redirects, login walls"]
    TECH --> TRUST["4. Trust pages<br/>About, Contact, Privacy with ad-cookie<br/>disclosures, Terms, authors, consent"]
    TRUST --> CONTENT["5. Content<br/>triage every page: keep / improve /<br/>merge / rewrite / remove<br/>CORE-EEAT score on 3–5 key pages"]
    CONTENT --> POLICY["6. Policy scan<br/>prohibited or restricted content,<br/>deceptive UX, 'click the ads' copy"]
    POLICY --> FULL["7. Fill all 73 AdSense IDs<br/>Pass / Fail / Unknown / N/A with evidence"]
    FULL --> REJ{"Rejected?"}
    REJ -->|"Yes"| MAPMSG["8. Map the exact message<br/>to causes via the rejection playbook"]
    REJ -->|"No"| DEC
    MAPMSG --> DEC{"9. Decision"}
    DEC --> OUT["ADSENSE-READINESS-REPORT.md<br/>decision, ordered fix list,<br/>73-ID table, unknowns"]
```

**How to run it**

> Use adsense-readiness-checker on https://example.in. Stage: rejected, message "Low value content". Traffic is organic plus Instagram. No existing AdSense account.

**What you get:** a decision line, Blocker and High counts, the top 5 fixes (each naming the agent or person that should do it), and a list of **Unknowns** that need your AdSense dashboard, server access, or a mobile check.

**Keep in mind:** it never edits the site. Anything it can't observe, such as rendered mobile layout or pop-ups, is marked Unknown rather than guessed.

---

## 4. content-quality-rewriter

**Purpose:** audit content that is already written, rewrite it to pass the rules, re-audit it, and show the before/after.

```mermaid
flowchart TD
    IN["Input: files / URLs / pasted text<br/>site niche + audience<br/>optional: mode, your real material"] --> AUD["1. Baseline audit<br/>CORE-EEAT score and vetoes<br/>human-web-content editorial audit<br/>AI-slop scan, AdSense content rules"]
    AUD --> POL{"Prohibited content?"}
    POL -->|"Yes"| STOP(["Stop: report it"])
    POL -->|"No"| VER["2. Verify every factual claim<br/>verified / outdated / unverifiable"]
    VER --> TREAT{"3. Treatment"}
    TREAT -->|"Already good"| KEEP["Keep: light fixes only"]
    TREAT -->|"Duplicate or off-topic"| MERGE(["Recommend merge / drop"])
    TREAT -->|"Fixable"| IMP["Improve<br/>minimum effective edit"]
    TREAT -->|"Thin or AI-generic"| RW["Rewrite<br/>research the gaps first"]
    IMP --> EDIT
    RW --> EDIT["4. Edit in order:<br/>cut, verify, add substance,<br/>restructure, reword, keep voice<br/>TK where your material is needed"]
    EDIT --> RE["5. Re-audit"]
    RE --> PASS{"Veto or High<br/>findings left?"}
    PASS -->|"No"| OUT
    PASS -->|"Yes, round ≤ 2"| EDIT
    PASS -->|"Only your input can fix it"| OUT
    KEEP --> OUT["post.rewritten.md<br/>post.rewrite-report.md<br/>before/after, claims table, TK list"]
    OUT --> TITLE{"Title still matches?"}
    TITLE -->|"No"| SNIP(["Run serp-snippet-writer"])
```

**How to run it**

> Use content-quality-rewriter on content/posts/gst-for-freelancers.md and content/posts/upi-limits.md. Site: Indian personal-finance blog, audience Indian freelancers. I'm a CA with 6 years of practice; use that where it fits.

**What you get:** a rewritten copy next to each original (the original is never overwritten), plus a report with the before/after verdict, what was cut or added and why, every claim with its source, and the `[TK]` questions only you can answer.

**Keep in mind:** it stops after 2 fix rounds instead of polishing endlessly. If a page is already good, it tells you so and leaves it alone.

---

## 5. serp-snippet-writer

**Purpose:** everything the page shows in Google and on social: titles, descriptions, H1 check, slug, OG/Twitter tags, alt text, and JSON-LD. The titles must sound like a person wrote them.

```mermaid
flowchart TD
    IN["Input: pages + brand name<br/>optional: keyword, market,<br/>mode report or apply"] --> RULES["Load human-title-rules.md<br/>read-aloud test, ban lists,<br/>Google title and snippet facts"]
    RULES --> READ["1. Read the page<br/>its job, intent, real specifics,<br/>H1, current title and meta"]
    READ --> SERP["2. Look at the current SERP<br/>to differentiate, never copy"]
    SERP --> DRAFT["3. Draft 3 titles + 3 descriptions<br/>different angles"]
    DRAFT --> CHK{"4. Self-check<br/>sounds human? no banned phrases?<br/>true to page? length counted?"}
    CHK -->|"Fails"| DRAFT
    CHK -->|"Passes"| PICK["5. Pick one ★ with a reason"]
    PICK --> REST["6. H1 note, slug, OG/Twitter,<br/>canonical, robots, alt text,<br/>JSON-LD from visible content only"]
    REST --> LINT["7. schema_lint.py<br/>fix errors"]
    LINT --> DUP["8. Batch check<br/>no duplicate titles or descriptions"]
    DUP --> MODE{"Mode"}
    MODE -->|"report"| OUT1["snippets.md + slug.head.html"]
    MODE -->|"apply"| OUT2["Edits head tags in your files<br/>and lists every change"]
```

**What "human touch" means here:**

| AI-template title | Human title |
|---|---|
| How to File GST Returns: The Complete Guide (2026) | How to File GSTR-1 as a Freelancer, Step by Step |
| What Is TDS? Here's Everything You Need to Know | What TDS Is and When It's Deducted From Your Pay |

**How to run it**

> Use serp-snippet-writer on https://example.in/blog/ (all posts in the sitemap). Brand: Example Finance. Market: India, English. Report mode.

**Keep in mind:** a title can't promise more than the page delivers. If the content is the problem, it tells you to run `content-quality-rewriter` first.

---

## 6. adsense-content-loop

**Purpose:** create new pages from scratch. Each topic loops through research, writing, the quality audit, AdSense checks, and SERP markup until it passes the publish gate.

```mermaid
flowchart TD
    IN["Input: topics up to 5 + site/niche + audience<br/>optional: your real material, output folder"] --> INT{"All required<br/>inputs present?"}
    INT -->|"No"| ASK(["Stop: returns questions"])
    INT -->|"Yes"| SITE["Site-level AdSense pass<br/>once per run, cached"]
    SITE --> S1

    subgraph TOPIC["For each topic, iterations ≤ 3"]
        S1["Stage 1 · SEO research<br/>seo-geo: search, top results,<br/>gaps, primary sources, brief"]
        S1 --> ANGLE{"Original angle?"}
        ANGLE -->|"No"| DROP(["DROPPED"])
        ANGLE -->|"Yes"| S2["Stage 2 · Write<br/>human-web-content<br/>article.md"]
        S2 --> S3["Stage 3 · Quality audit<br/>content-quality-auditor<br/>CORE-EEAT score + vetoes"]
        S3 --> S4["Stage 4 · AdSense checks<br/>adsense-auditor page-level IDs"]
        S4 --> POLICY{"Policy hit?"}
        POLICY -->|"Yes"| PSTOP(["POLICY STOP"])
        POLICY -->|"No"| S5["Stage 5 · SERP + AI search<br/>geo-content-optimizer,<br/>serp-markup-builder, head.html"]
        S5 --> GATE{"Publish gate"}
    end

    GATE -->|"Pass"| READY(["READY FOR OWNER REVIEW"])
    GATE -->|"Sources or angle weak"| S1
    GATE -->|"Content or slop issues"| S2
    GATE -->|"Title or schema issues"| S5
    GATE -->|"Needs your material"| TK(["BLOCKED ON OWNER INPUT"])
    GATE -->|"Still failing after 3 rounds"| NR(["NOT READY"])

    READY --> REP["REPORT.md + per-topic folders<br/>research.md, article.md,<br/>head.html, audit.md"]
    TK --> REP
    NR --> REP
    DROP --> REP
    PSTOP --> REP
```

**How to run it**

> Use adsense-content-loop: 3 articles — "GSTR-1 for freelancers", "UPI transaction limits by bank", "Section 44ADA explained". Site example.in, Indian freelancers. Author: CA, 6 years' practice. Output: ./content/.

**What you get:**

```
content/
  REPORT.md
  gstr-1-freelancers/
    research.md   brief, sources, SERP notes
    article.md    the page
    head.html     title, meta, OG, JSON-LD
    audit.md      scores, AdSense checks, gate log, TK list
```

**Keep in mind:** it never publishes. Every page ends at *ready for your review*, and anything that needs your real experience becomes a `[TK]` question.

---

## 7. Skills each agent uses

"Pre" means the skill is loaded at startup; "✓" means the agent calls it at the step that needs it.

| Skill | readiness-checker | quality-rewriter | snippet-writer | content-loop |
|---|:-:|:-:|:-:|:-:|
| `adsense-auditor` | **pre** | ✓ | | ✓ |
| `adsense-content-pipeline` | ✓ | | | **pre** |
| `human-web-content` | ✓ | **pre** | ✓ | ✓ |
| `clarity` | | ✓ | | ✓ |
| `content-quality-auditor` | ✓ | ✓ | | ✓ |
| `geo-content-optimizer` | | | | ✓ |
| `serp-markup-builder` | | | **pre** | ✓ |
| `seo-geo` | ✓ | | | ✓ |
| `pagewell` | | | | ✓ (repos only) |

```mermaid
flowchart LR
    subgraph AGENTS["Agents"]
        RC["readiness-checker"]
        QR["quality-rewriter"]
        SW["snippet-writer"]
        CL["content-loop"]
    end
    subgraph SKILLS["Skills"]
        AA["adsense-auditor"]
        PL["adsense-content-pipeline"]
        HW["human-web-content"]
        CQ["content-quality-auditor"]
        GO["geo-content-optimizer"]
        SM["serp-markup-builder"]
        SG["seo-geo"]
    end
    RC --> AA & PL & CQ & SG
    QR --> HW & CQ & AA
    SW --> SM & HW
    CL --> PL & SG & HW & CQ & AA & GO & SM
```

---

## 8. Rules every agent follows

When skills disagree, this order wins (from `adsense-content-pipeline`):

```mermaid
flowchart TD
    R1["1 · Live Google docs + adsense-auditor"] --> R2["2 · Truth: nothing invented"]
    R2 --> R3["3 · Writing style: human-web-content / clarity"]
    R3 --> R4["4 · Scoring: content-quality-auditor + local overrides"]
    R4 --> R5["5 · SEO/GEO tactics: seo-geo, geo-content-optimizer"]
```

- **Nothing invented:** no fake stats, quotes, experiences, reviewers, ratings, or dates. Gaps become `[TK: question]` for you.
- **No approval promises:** AdSense approval is Google's decision.
- **No bulk pages:** at most 5 topics per run.
- **No mid-run questions:** agents can't ask you anything while running. If inputs are missing, they stop at once and return their questions.
- **No publishing:** agents never publish, apply to AdSense, or push to a live site.

---

## 9. Install and run

```bash
# from this repo's root
cp agents/*.md ~/.claude/agents/
cp -r skills/* ~/.claude/skills/
```

On Windows, the target is `C:\Users\<you>\.claude\agents\` and `...\.claude\skills\`. Restart Claude Code afterwards so it picks them up.

Then just ask in plain words; Claude hands the job to the agent whose description matches:

| Say | Runs |
|---|---|
| "Is example.in ready for AdSense?" | `adsense-readiness-checker` |
| "Check and rewrite these 3 posts" | `content-quality-rewriter` |
| "Rewrite the titles and meta for my blog, make them sound human" | `serp-snippet-writer` |
| "Write 3 AdSense-ready articles on …" | `adsense-content-loop` |

You can also name the agent directly: *"Use serp-snippet-writer on …"*.
