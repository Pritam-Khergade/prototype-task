# Lens — Output Intelligence Layer for Claude
## AI Prompts Used · Organized by Use Case

> **Growth Team · Claude · PM Assignment**
>
> This document records all AI tool prompts used in developing the Lens product proposal, organized by use case. Each entry shows the exact prompt text, its purpose, and the tool it was used with. All prompts involving user research data were run with fully anonymized inputs — no sensitive prompts, personal identifiers, or private user outputs are included.

---

## Table of Contents

1. [Market & Landscape Research](#01--market--landscape-research-prompts)
2. [User Research & Interview Synthesis](#02--user-research--interview-synthesis-prompts)
3. [User Journey & Problem Framing](#03--user-journey--problem-framing-prompts)
4. [Solution Ideation](#04--solution-ideation-prompts)
5. [UI Generation](#05--ui-generation-prompts)
6. [Metrics Design & Self-Critique](#06--metrics-design--self-critique-prompts)
7. [Ethical Research Practices](#notes-on-ethical-research-practices)

---

## 01 · Market & Landscape Research Prompts

> Used to understand the existing market, competitor approaches, and gaps in AI output evaluation.

---

### Market landscape

**Prompt**
```
You are a product researcher. Map the current landscape of AI output evaluation
tools — including hallucination detection, fact-checking layers, confidence
indicators, citation tools, and explainability features. For each approach,
describe: what it does, who offers it, what it solves, and where it fails to
address the core trust problem. Format as a structured comparison.
```

**Purpose:** Understand what solutions already exist and identify the whitespace Lens could occupy.

**Tool:** Claude Sonnet

---

### Gap analysis

**Prompt**
```
Why do current AI trust and evaluation systems fail to solve the core problem
of calibration — i.e., helping users develop accurate intuition about when to
trust AI outputs and when to question them? Focus specifically on: (1) the
difference between output quality and perceived quality, (2) why fact-checking
alone is insufficient, (3) what is fundamentally missing from existing
approaches.
```

**Purpose:** Identify the unmet need that distinguishes Lens from existing solutions.

**Tool:** Claude Sonnet

---

### Literature scan

**Prompt**
```
Summarize what academic and industry research says about how non-expert users
evaluate information quality — including cognitive biases that lead to
over-trust of polished, well-formatted content. What does research say about
calibration in human-AI interaction? Include relevant findings from HCI,
cognitive psychology, and AI alignment.
```

**Purpose:** Ground the problem definition in existing research on human evaluation behavior.

**Tool:** Claude Sonnet + web search

---

### Competitor teardown

**Prompt**
```
Analyze how the following products currently handle AI output quality
signaling: (1) Perplexity AI citations, (2) Bing Copilot confidence
indicators, (3) Google Bard source attribution, (4) Notion AI. For each:
what signals do they surface, what do users do with those signals, and what
is the biggest remaining gap? Be critical — assume current implementations
are partial solutions.
```

**Purpose:** Identify specific feature-level gaps that validate Lens's differentiated approach.

**Tool:** Claude Sonnet

---

## 02 · User Research & Interview Synthesis Prompts

> Used to design research instruments, synthesize interview findings, and extract patterns from user sessions.

---

### Interview guide

**Prompt**
```
Design a user interview guide for a 45-minute in-depth interview with
knowledge workers who regularly use Claude or ChatGPT for research, writing,
or analysis. The goal is to understand: (1) how they currently evaluate AI
outputs, (2) what signals they use to decide whether to trust an output,
(3) where they get things wrong, (4) what they fail to notice. Include 2
task-based observation scenarios where the user works through a real AI
output in real-time. All questions should be open-ended and non-leading.
```

**Purpose:** Create a rigorous, unbiased research instrument for the 7 in-depth interviews.

**Tool:** Claude Sonnet

---

### Think-aloud protocol

**Prompt**
```
Write a think-aloud observation protocol for watching users interact with an
AI-generated research summary. I want to observe: where they pause or
re-read, what they accept without questioning, what makes them feel confident
vs. uncertain, and whether they notice missing information or weak reasoning.
Include a pre-task briefing script and a structured debrief with 5 probing
questions.
```

**Purpose:** Design the task-based observation sessions that complement the semi-structured interviews.

**Tool:** Claude Sonnet

---

### Synthesis — patterns

**Prompt**
```
Here are anonymized notes from 7 user interviews about how people evaluate
AI-generated outputs. [Notes pasted in — anonymized, no sensitive content.]
Synthesize the key patterns: (1) What do users consistently trust without
checking? (2) What evaluation behaviors are common vs. rare? (3) What
cognitive shortcuts do users rely on? (4) Where does evaluation completely
break down? Name each pattern clearly and provide supporting evidence from
the notes. Do not invent patterns not supported by the data.
```

**Purpose:** Extract structured insights from raw interview notes to inform the problem definition.

**Tool:** Claude Sonnet

---

### Survey design

**Prompt**
```
Design a 12-question survey (n=30 target) to validate patterns found in user
interviews about AI output evaluation behavior. The survey should measure:
(1) how often users re-read or critically examine AI outputs, (2) what
signals they use to judge quality, (3) how confident they feel in their own
evaluation ability, (4) whether they have ever acted on a flawed AI output
and what happened. Include a mix of Likert scale, multiple choice, and one
open-ended question. Avoid leading language.
```

**Purpose:** Design the quantitative validation instrument to complement qualitative interviews.

**Tool:** Claude Sonnet

---

### Survey analysis

**Prompt**
```
Here are responses from a 32-person survey on AI output evaluation behavior.
[Survey data — anonymized.] Analyze the data and identify: (1) the most
common trust behaviors, (2) where over-trust is most prevalent, (3) what
percentage of users actively check for missing context vs. only evaluating
what is present, (4) any surprising findings. Present key statistics and
highlight the 3 most important insights for a product team building an
evaluation layer for Claude.
```

**Purpose:** Extract actionable product insights from the survey results.

**Tool:** Claude Sonnet + data analysis

---

## 03 · User Journey & Problem Framing Prompts

> Used to map the end-to-end user journey, identify breakdown points, and frame the core problem.

---

### Journey map

**Prompt**
```
Map the full user journey for a knowledge worker using Claude for a
high-stakes task (e.g., market research for a business decision). Cover 5
stages: (1) prompting, (2) output generation, (3) first read / interpretation,
(4) evaluation, (5) action / use. For each stage, describe: what the user is
thinking and doing, what they trust, what they question, and where trust or
judgment typically breaks down. Be specific — use concrete examples of what
goes wrong at each stage.
```

**Purpose:** Identify the specific stages where Lens needs to intervene most.

**Tool:** Claude Sonnet

---

### Failure mode map

**Prompt**
```
Given this user journey map for AI-assisted research, identify the 3
highest-risk breakdown points where users are most likely to: (1) over-trust
a weak or incomplete output, (2) fail to notice missing context, or (3) take
action based on flawed reasoning. For each breakdown point, describe: what
specifically goes wrong, why it happens (cognitive or UX factors), and what
the downstream consequences are.
```

**Purpose:** Prioritise which stages of the journey Lens should address first in v1.

**Tool:** Claude Sonnet

---

### Problem statement

**Prompt**
```
Based on this user research synthesis, write a precise product problem
statement for the following context: knowledge workers using Claude for
high-stakes tasks cannot reliably evaluate whether AI outputs are correct,
complete, or well-reasoned — leading to either over-trust or excessive
skepticism. The problem statement should: identify the specific user, the
specific failure, the root cause, and the cost to the user. Avoid generic
framing. The statement should be specific enough to evaluate solutions
against.
```

**Purpose:** Produce a tight, testable problem statement to anchor the product brief.

**Tool:** Claude Sonnet

---

## 04 · Solution Ideation Prompts

> Used to explore solution directions, stress-test ideas, and justify the chosen approach.

---

### Solution directions

**Prompt**
```
Generate 5 distinct product solution directions for this problem: knowledge
workers using Claude cannot reliably evaluate AI output quality, leading to
miscalibrated trust. Each direction should be genuinely different in its
mechanism and user model — not just variations on the same idea. For each:
name it, describe the core mechanism, describe the user interaction, explain
what problem it uniquely solves, and identify its biggest weakness. Include
at least one direction that seems counterintuitive.
```

**Purpose:** Explore the solution space before converging on a direction.

**Tool:** Claude Sonnet

---

### Direction comparison

**Prompt**
```
Compare these 3 solution directions for improving AI output trust calibration:
(1) inline annotation layer with confidence highlights, (2) a separate
evaluation panel with structured quality scores, (3) a calibration training
mode with practice exercises. Evaluate each on: user trust impact, AI
feasibility, business value, risk of creating dependence vs. building
judgment, and fit with Claude's product principles. Recommend one primary
direction and one complementary direction. Show your reasoning.
```

**Purpose:** Make a structured, justifiable choice between competing solution directions.

**Tool:** Claude Sonnet

---

### Feature specification

**Prompt**
```
Design the detailed feature specification for an AI output evaluation layer
called Lens, integrated into Claude's chat interface. The feature must:
(1) surface inline signals on weak reasoning, missing context, and uncertainty
without cluttering the output, (2) provide a structured evaluation panel with
multi-dimensional quality scores, (3) include a calibration mode to build
user evaluation skills over time, (4) never present itself as the final
authority — always support human judgment. Define the exact user interactions,
information architecture, and key design principles. Include edge cases:
conflicting signals, overconfident AI responses, incomplete reasoning.
```

**Purpose:** Create the product specification that drives design and engineering decisions.

**Tool:** Claude Sonnet

---

### Anti-patterns

**Prompt**
```
What are the 5 most dangerous ways an AI output evaluation feature like Lens
could fail or cause harm — specifically by: creating a new form of blind
trust (trust in the scores), introducing cognitive overload that reduces
usage, creating circular AI-evaluates-AI validation, patronizing expert users
while confusing beginners, or reducing user agency by framing scores as
verdicts. For each failure mode: describe exactly how it happens, how serious
it is, and what specific design decisions would prevent it.
```

**Purpose:** Identify failure modes proactively to design mitigations into the solution from the start.

**Tool:** Claude Sonnet

---

## 05 · UI Generation Prompts

> Used to generate the interactive prototype, slide deck, and visual assets.

---

### Prototype — chat UI

**Prompt**
```
Build a fully clickable HTML prototype of the Lens feature integrated into a
Claude-style chat interface. The prototype must include: (1) a chat panel
with a user message and an AI response containing inline color-coded highlight
spans for different flag types (weak reasoning = amber underline, missing
context = red dotted, uncertain = purple dashed, well-grounded = green solid),
(2) hover tooltips on each highlight explaining the flag, (3) a right-side
Lens evaluation panel with collapsible sections: quality scores (correctness,
completeness, reasoning, usefulness), flags to review, alternative
perspectives, and reasoning trace, (4) action chip buttons that simulate
follow-up conversations. Use a navy/teal color palette. No frameworks —
pure HTML/CSS/JS.
```

**Purpose:** Build the clickable prototype for the PM assignment deliverable.

**Tool:** Claude Sonnet (this session)

---

### Prototype — calibration mode

**Prompt**
```
Add a Calibration Mode screen to the Lens prototype. It should include:
(1) a domain selector (Research, Writing, Career prep, Code review), (2) a
3-exercise practice flow with an AI output snippet, a multiple-choice question
about the flaw, color-coded feedback on selection (green = correct, red =
wrong, reveal correct answer), (3) a progress bar and dot tracker, (4) a
personalized insight card that appears after completing all 3 exercises.
Exercises should cover real evaluation skills: spotting overgeneralization,
identifying causal claim weakness, and recognizing overconfident conclusions.
```

**Purpose:** Demonstrate the calibration layer of the Lens product in the prototype.

**Tool:** Claude Sonnet (this session)

---

### Slide deck

**Prompt**
```
Create a 10-slide .pptx presentation deck for a PM assignment on the Lens
product proposal. Each slide title must state the key message (not the
category). Slides: (1) Title, (2) problem statement, (3) user research
findings, (4) target segment and unmet needs, (5) user journey with
breakdown points, (6) solution overview — 3 layers of output intelligence,
(7) system design and key principles, (8) business impact and trade-offs,
(9) success metrics with north star and guardrails, (10) self-critique —
why Lens might fail. Use a navy/teal palette. No fellow name anywhere.
Minimum 14pt font. Colorblind-safe palette.
```

**Purpose:** Generate the slide deck deliverable for the PM assignment.

**Tool:** Claude Sonnet (this session) + pptxgenjs

---

### Inline annotation design

**Prompt**
```
Design the visual language for inline annotation spans in the Lens output.
I need 4 distinct annotation types that are immediately distinguishable but
not visually overwhelming: (1) well-grounded / high confidence, (2) weak
reasoning / oversimplified claim, (3) missing context / material gap,
(4) high uncertainty. For each: specify background color, underline style
(solid/dotted/dashed), underline color, and a short tooltip label. The design
should work on white backgrounds, be colorblind-accessible, and feel native
to a chat interface rather than a code editor.
```

**Purpose:** Define the visual design system for the core Lens inline signal layer.

**Tool:** Claude Sonnet

---

## 06 · Metrics Design & Self-Critique Prompts

> Used to define success metrics, stress-test the solution, and produce the self-critique section.

---

### North star metric

**Prompt**
```
Design the success metrics framework for Lens, an AI output evaluation layer
for Claude. The north star metric must capture the core outcome — not just
usage, but actual improvement in user calibration. Propose: (1) one north
star metric with a clear definition and how it would be measured, (2) 4
leading indicators that predict north star movement, (3) 2 guardrail metrics
that would signal the feature is causing harm (e.g., over-dependence on
scores, cognitive overload leading to disengagement). For each metric: define
it precisely, explain why it matters, and give a target range.
```

**Purpose:** Create a rigorous, outcome-focused measurement framework for the Lens feature.

**Tool:** Claude Sonnet

---

### Trade-off analysis

**Prompt**
```
Analyze the key product trade-offs for Lens: (1) speed vs. accuracy — how
much latency is acceptable for evaluation quality? (2) assistance vs.
dependence — how do you help users evaluate without making them dependent on
scores? (3) transparency vs. cognitive overload — how much information is too
much? For each trade-off: explain the tension, describe the user impact of
getting it wrong in each direction, and propose specific design decisions that
manage the trade-off without fully resolving it.
```

**Purpose:** Surface and address trade-offs in the business case slide and solution design.

**Tool:** Claude Sonnet

---

### Self-critique

**Prompt**
```
You are a skeptical senior PM reviewing the Lens product proposal. Your job
is to identify the 5 most serious ways this product could fail or cause harm
— specifically failure modes that are non-obvious and hard to detect. For
each: (1) describe exactly how the failure happens in a realistic scenario,
(2) rate the severity (critical / high / medium), (3) explain why it is hard
to catch, (4) propose a specific mitigation that is built into the product
design rather than handled post-launch. Do not give generic product risks —
be specific to Lens.
```

**Purpose:** Generate the self-critique section and build genuine mitigations into the product design.

**Tool:** Claude Sonnet

---

### Business case

**Prompt**
```
Write the business case for Lens as a Claude Growth Team initiative. Focus
on: (1) how solving calibrated trust directly impacts D30 retention for
knowledge worker users, (2) how Lens creates a path to higher-stakes workflow
adoption and enterprise upsell, (3) the competitive moat — why this is hard
to replicate and how it deepens Claude's differentiation. Be specific about
the mechanism — not just "users will trust more" but the exact behavioral
change and why it compounds over time. Acknowledge the risk that Lens could
create a new form of dependence if executed poorly.
```

**Purpose:** Build the business impact argument for the business case slide.

**Tool:** Claude Sonnet

---

## Notes on Ethical Research Practices

All prompts involving user research data were run with **fully anonymized inputs**. No sensitive prompts, personal identifiers, or private user outputs were shared with AI tools at any point.

- Interview participants provided **explicit verbal consent** for session recordings and synthesis
- All synthesized outputs were reviewed before use to ensure **no re-identification** was possible
- Survey responses were anonymized before being passed to any AI tool for analysis
- No real user names, organizations, or identifying details appear in any prompt or output

---

*20 prompts · 6 use case categories · Claude Sonnet · Lens PM Assignment*
