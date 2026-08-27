<div align="center">

# 🌿 Body Root Cause

### System-level supplement decision support for AI agents

**Map the problem. Update the evidence. Test one variable. Learn from the result.**

[![Version](https://img.shields.io/badge/version-2.2-2563EB?style=for-the-badge)](./body-root-cause/SKILL.md)
[![Language](https://img.shields.io/badge/core-English-111827?style=for-the-badge)](./body-root-cause/SKILL.md)
[![License](https://img.shields.io/github/license/JackZhong2017/body-root-cause-skill?style=for-the-badge)](./LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/JackZhong2017/body-root-cause-skill?style=for-the-badge)](https://github.com/JackZhong2017/body-root-cause-skill/stargazers)

A portable `SKILL.md` for generally healthy adults with everyday health concerns or supplement questions. It uses structured intake, qualitative Bayesian updating, and longitudinal records to turn vague symptoms into a cautious, testable next step.

[Quick start](#quick-start) · [How it works](#how-it-works) · [What changed in v2.2](#what-changed-in-v22) · [Installation](#installation) · [Safety](#safety)

</div>

---

## Why this skill exists

Health questions often begin with a symptom and jump directly to a supplement. That shortcut can produce confident stories, oversized stacks, and results that are impossible to attribute.

Body Root Cause follows a tighter decision loop:

```text
Concern
   ↓
Confirmed facts + relevant system scan
   ↓
Leading hypothesis + competing explanation
   ↓
Highest-value question, observation, or test
   ↓
One attributable action
   ↓
Measured follow-up → global update
```

The goal is practical judgment under uncertainty. The skill can recommend observation, a lifestyle change, a decision-changing test, a single supplement trial, or clinical evaluation.

## Quick start

```bash
npx skills add https://github.com/JackZhong2017/body-root-cause-skill --skill body-root-cause
```

Then ask a decision-oriented question:

```text
I have been tired lately. Should I check iron or vitamin B12 first?

My sleep is poor. Which is a better fit: magnesium, glycine, or L-theanine?

I keep getting bloated. Should I continue taking a probiotic?

My vitamin D result is low. How should I supplement and retest?
```

The internal operating layer is English. Questions and visible answers follow the user's current language unless another language is requested.

## How it works

### 1. Define the decision

The skill first identifies whether the user needs concern assessment, supplement selection, result interpretation, follow-up, or general knowledge.

### 2. Scan only relevant systems

It considers the domains that could change the action:

| Domain | Examples of decision-relevant information |
|---|---|
| Sleep and recovery | Sleep opportunity, schedule, training recovery, recent infection |
| Intake and nutrition | Energy intake, protein, restrictions, measured deficiency risk |
| Medications and supplements | Starts, stops, dose changes, duplicate ingredients, interactions |
| Metabolic and endocrine context | Weight trend, menstrual context, glucose-related clues, existing tests |
| Digestion and absorption | Bowel pattern, persistent GI concerns, food relationships, absorption limits |
| Stress and behavior | Stress timeline, caffeine, alcohol, routines, maintaining loops |
| Environment and routine | Travel, work pattern, exposures, food environment, activity changes |

A domain is a search area. It becomes a candidate explanation only when individual evidence connects it to the concern.

### 3. Update evidence qualitatively

Each candidate is evaluated through:

- baseline basis;
- supporting evidence;
- opposing evidence;
- unknown information;
- competing explanations;
- decision impact.

Evidence updates are labeled **strong**, **moderate**, **weak**, or **no update**. The skill does not manufacture percentages from arrows, scores, or wording intensity.

### 4. Preserve uncertainty that matters

Visible output separates:

```text
Confirmed facts
Leading hypothesis
Competing hypothesis
Highest-value next information
Current action
Next candidate
Safety and clinical boundary
```

A leading hypothesis remains an inference. A plausible mechanism does not automatically become a proven root cause or a supplement recommendation.

### 5. Test one variable

A supplement trial defines the target, rationale, protocol, review window, outcome measures, stop rules, and constraints. Deferred options remain under **Next candidate** instead of becoming a simultaneous shopping list.

## What changed in v2.2

| Previous limitation | v2.2 behavior |
|---|---|
| Arrow-based weights implied precision without calculation | Qualitative Bayesian updates include supporting, opposing, and missing evidence |
| One symptom or body location could dominate the conclusion | Single manifestations provide at most a weak update |
| A fixed acne-centered hypothesis library narrowed the reasoning | Relevant system domains are selected from the user's actual concern |
| "Root cause" could appear before alternatives were tested | Output preserves leading and competing hypotheses until evidence supports stronger language |
| Multi-supplement plans obscured attribution | One new variable is tested at a time with predefined measures and stop rules |
| Internal instructions depended on Chinese | The complete operating layer and canonical record schema are English |

## Longitudinal health record

When the environment supports files, the default record is:

```text
~/.health-records/medical-record.md
```

It can store:

- baseline constraints;
- laboratory values with date, unit, and reference range;
- medication and supplement starts/stops;
- concern history;
- intervention outcomes and concurrent changes.

Canonical fields are English for portability across models. The skill asks for consent before writing and does not load a user's record for third-party questions.

## Installation

The repository packages the skill as a self-contained directory:

```text
body-root-cause-skill/
├── body-root-cause/
│   └── SKILL.md
├── LICENSE
└── README.md
```

### Codex

Copy `body-root-cause/` to:

```text
~/.codex/skills/body-root-cause/
```

For project-scoped use, place it under the project's `.codex/skills/` directory.

### Claude Code

Copy `body-root-cause/` to:

```text
~/.claude/skills/body-root-cause/
```

For project-scoped use, place it under the project's `.claude/skills/` directory.

### OpenClaw

```bash
openclaw skills install https://github.com/JackZhong2017/body-root-cause-skill
```

Add `--global` when a global installation is appropriate.

### Other agents

Use the repository with any agent that supports portable `SKILL.md` instructions. Keep the `body-root-cause/SKILL.md` path intact unless the host defines another skill-directory convention.

## Boundaries

Body Root Cause is designed for:

- everyday health concerns in generally healthy adults;
- deciding whether a supplement trial is justified;
- choosing the next useful question, measurement, or test;
- tracking one-variable interventions over time;
- explaining why the evidence is insufficient to act.

It does not:

- diagnose disease;
- replace a clinician;
- direct prescription-medication changes;
- run the adult supplement workflow for children;
- provide topical skincare recommendations;
- infer an individual cause from a population association, one symptom, or an anecdote.

## Safety

This repository provides an AI reasoning workflow, not medical care. Supplement decisions can be affected by diagnosed conditions, pregnancy, medications, allergies, total intake, and product quality.

If a concern needs diagnosis or prescription treatment, keeps worsening, substantially impairs daily function, or involves an acute serious manifestation, clinical evaluation is the appropriate next step.

## Contributing

Focused improvements are welcome. Changes should preserve the core invariants:

1. distinguish facts from hypotheses;
2. keep decision-relevant alternatives;
3. avoid unsupported numerical confidence;
4. prefer one attributable intervention;
5. keep the internal operating layer in English;
6. preserve the final safety boundary.

## License

[MIT](./LICENSE) © 2026 jjjjjjjjjjjjack
