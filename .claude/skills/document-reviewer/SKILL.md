---
name: document-reviewer
description: Use this skill when the user wants to review, proofread, audit, or critique
  a document. Triggers on phrases like "review this document", "give feedback on",
  "proofread", "check this for me", "audit this doc", "what's wrong with this",
  "improve this document", "is this ready to send", "review for clarity/tone/structure",
  or any variation where the goal is evaluating or improving existing written content.
  Supports PDF, DOCX, TXT, MD, and plain pasted text. Covers tone, structure,
  clarity, completeness, and language quality. Do NOT trigger for document creation
  from scratch — use the appropriate docx/pdf/md skill instead.
---

# Document Review Skill

## Why this skill exists

Reviewing a document well requires a consistent approach. Without structure,
feedback becomes scattered, vague, or biased toward surface-level issues while
missing deeper problems. This skill enforces a repeatable review protocol.

---

## PRIMACY — Read this first

**Before reviewing, establish two things:**

1. **What type of review does the user want?**
   If not specified, default to: structure + clarity + language. Ask only if the
   document type strongly suggests a specialist lens (legal, technical spec, etc.).

2. **What is the document's purpose and audience?**
   A client-facing proposal is judged differently from an internal memo.
   If context is missing and it matters, ask one question before proceeding.

**Never do all review modes at full depth unless explicitly asked.** Pick the
most relevant 2-3 lenses based on document type and user intent.

---

## Review modes

| Mode | When to apply | What to check |
|---|---|---|
| **Structure** | Default | Logical flow, section order, missing parts, weak opening/closing |
| **Clarity** | Default | Ambiguous sentences, jargon without definition, buried key points |
| **Language** | Default | Grammar, spelling, punctuation, tone consistency, word choice |
| **Completeness** | Specs, proposals, reports | Missing context, unanswered questions, unsupported claims |
| **Tone** | Client-facing, formal docs | Register consistency, appropriate formality, assertiveness |
| **Technical accuracy** | Technical/domain docs | Factual plausibility (flag, don't invent corrections) |

---

## Protocol

### Step 1 — Read the document

Use `file-reading` skill to load the file if uploaded. For pasted text, proceed directly.

Always do a full read before writing any feedback. Do not comment as you go.

### Step 2 — Orient

Note:
- Document type (email, report, proposal, spec, article, etc.)
- Estimated length and complexity
- Apparent purpose and audience (if determinable)

State this briefly at the top of your review output.

### Step 3 — Structured feedback

Output feedback in this order:

**1. Summary verdict (2-3 sentences)**
Overall impression. Is it ready? What is the single most important thing to fix?

**2. Structural issues**
Number each finding. Reference specific sections or paragraph positions.
Focus on impact, not just presence of the issue.

**3. Clarity issues**
Same: numbered, located, impactful.

**4. Language issues**
Group minor grammar/spelling into a single block unless a pattern is significant.
Do not list every typo individually unless the document is short.

**5. Positives (optional but useful)**
One or two things that work well. Keeps feedback balanced and actionable.

**6. Priority action list**
Max 5 items ranked by impact. These are the things to fix before anything else.

### Step 4 — Offer a revision

After feedback, always offer:
> "Want me to apply these changes and produce a revised version?"

---

## Output format rules

- Use numbered findings, not bullet soup
- Reference location by section name or paragraph number (e.g. "Para 3", "Intro section")
- Be direct. "This sentence is unclear because..." beats "You might consider..."
- Flag assumptions explicitly: "I'm assuming this is for a Dutch B2B audience"
- Do not rewrite the full document unless asked

---

## Document type guidance

**Emails / short messages**
Focus on: tone, clarity, clear call to action. Skip structural review unless multi-part.

**Proposals / pitches**
Focus on: completeness, structure, tone. Does it answer "why you, why now, what's in it for me"?

**Technical specs / functional designs**
Focus on: completeness, unambiguous requirements, missing edge cases. Flag factual
claims you cannot verify rather than inventing corrections.

**Reports / analyses**
Focus on: structure, supported claims, executive summary quality, conclusion strength.

**Formal letters / contracts (non-legal)**
Focus on: tone, precision of language, completeness. Flag anything that looks
legally significant with: "This may have legal implications — verify with appropriate counsel."

---

## RECENCY — Hard rules

- Never invent facts to fill gaps in a document. Flag them as missing.
- Never rewrite the entire document unprompted. Offer it, don't do it.
- If the document contains sensitive personal or financial data, do not quote
  it back verbatim in feedback. Reference it by position only.
- If the review mode was not specified and the document type is ambiguous,
  ask one focused question before proceeding. One. Not three.