# Body Root Cause Skill

![GitHub stars](https://img.shields.io/github/stars/JackZhong2017/body-root-cause-skill?style=flat-square)
![License](https://img.shields.io/github/license/JackZhong2017/body-root-cause-skill?style=flat-square)
![Skill](https://img.shields.io/badge/Skill-Agent-111111?style=flat-square)
![Claude Code](https://img.shields.io/badge/Claude%20Code-Supported-6B5B95?style=flat-square)
![OpenClaw](https://img.shields.io/badge/OpenClaw-Supported-2E8B57?style=flat-square)

> 🇨🇳 **中文版: [README.md](./README.md)**

A Claude Skill for diagnosing internal (supplement-level) health issues using **evidence-based nutrition + Bayesian reasoning**, helping you trace problems back to their systemic root cause instead of just treating symptoms.

## Quick Start (30 seconds)

```bash
npx skills add https://github.com/JackZhong2017/body-root-cause-skill --skill body-root-cause
```

Or just send this to an AI agent with shell access:

```text
Please install body-root-cause. Clone https://github.com/JackZhong2017/body-root-cause-skill into ~/.claude/skills/body-root-cause, then verify SKILL.md exists.
```

To update an existing install:

```text
Please update body-root-cause. Run git pull inside ~/.claude/skills/body-root-cause, then tell me the latest commit.
```

## What problems does it solve

It doesn't just tell you "what to take" — it first helps you understand "why this is happening".

**Skin issues**
- Recurring acne/closed comedones that don't respond to topical treatment
- Jawline/chin breakouts (possibly hormonal or PCOS-related)
- Sudden skin flare-ups after travel or moving to a new city
- Hyperpigmentation, oily skin, sensitivity with an unclear root cause

**General supplement decisions**
- Poor sleep — unsure whether to choose magnesium, L-theanine, or glycine
- Frequent fatigue — unsure if it's iron deficiency, B12 deficiency, or something else
- Want to start with basic supplements but don't know where to begin
- Supplement stacks for fitness, pregnancy prep, PCOS, and other specific scenarios

## How it works

```
Intake questions → Bayesian weight updates → Root cause localization → Tiered intervention plan
```

**7 root-cause hypotheses**, systematically ruled in or out:

| Hypothesis | Root Cause |
|------|------|
| H1 | Androgenic acne (hormone-driven) |
| H2 | PCOS / insulin resistance |
| H3 | Elevated cortisol (stress-driven) |
| H4 | Gut dysbiosis / H. pylori |
| H5 | Nutrient deficiency (zinc/vitamin D/Omega-3) |
| H6 | Environmental trigger (water quality/pollution/diet change) |
| H7 | Skincare/medication-induced |

**Output covers three layers** — addressing only triggers leads to recurrence, addressing only root causes is slow to show results:

- **Root Cause**: long-standing systemic issue
- **Trigger**: short-term external event
- **Perpetuating Factor**: condition that keeps the problem going

## Installation

### Claude Code

**Option 1: One-line CLI install (recommended)**

```bash
# Personal global install (available across all projects)
mkdir -p ~/.claude/skills && \
  git clone https://github.com/JackZhong2017/body-root-cause-skill.git /tmp/brc-skill && \
  cp -r /tmp/brc-skill/body-root-cause ~/.claude/skills/body-root-cause

# Windows (PowerShell)
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills"
git clone https://github.com/JackZhong2017/body-root-cause-skill.git "$env:TEMP\brc-skill"
Copy-Item -Recurse "$env:TEMP\brc-skill\body-root-cause" "$env:USERPROFILE\.claude\skills\body-root-cause"
```

**Option 2: Manual install**

1. Download this repo: `Code → Download ZIP`, then unzip
2. Copy the `body-root-cause` folder to:

| OS | Path |
|------|------|
| macOS / Linux | `~/.claude/skills/body-root-cause/` |
| Windows | `%USERPROFILE%\.claude\skills\body-root-cause\` |

3. Make sure the directory structure is `skills/body-root-cause/SKILL.md` (no extra nesting)
4. Restart Claude Code and run `/skills` to confirm it loaded

> **Project-level install**: place the folder under `.claude/skills/body-root-cause/` inside a project to scope it to that project only.

---

### OpenClaw

**Option 1: Paste the GitHub link directly**

Send in chat:
```
Install this skill: https://github.com/JackZhong2017/body-root-cause-skill
```
OpenClaw will detect and install it automatically.

**Option 2: CLI install**

```bash
# Install into the current workspace
openclaw skills install https://github.com/JackZhong2017/body-root-cause-skill

# Global install (available to all agents)
openclaw skills install https://github.com/JackZhong2017/body-root-cause-skill --global
```

**Option 3: Install via ClawHub** (once listed)

```bash
clawhub install body-root-cause
```

---

### Example prompts

Once installed, just ask in chat — the skill triggers automatically:

```
My acne keeps coming back, what should I take to improve it?
Why do I keep getting breakouts on my chin?
Help me put together a supplement plan for PCOS
My sleep is bad — which is better for me: magnesium, L-theanine, or glycine?
I'm often tired — not sure if it's iron deficiency, B12 deficiency, or something else
I want to start with basic supplements but don't know where to begin
```

## Important notes

- This skill does **not provide medical diagnosis** — supplement recommendations are not a substitute for prescription medication
- If symptoms keep worsening, or show no response after 3 months of standard intervention, seek medical care first
- All recommended ingredients must meet a baseline of credible clinical evidence (RCT or systematic review support)
- Strictly limited to internal/supplement recommendations — does not output topical skincare advice

## License

MIT © 2026 jjjjjjjjjjjjack — free to use, modify, and use commercially, with the copyright notice retained. See [LICENSE](LICENSE) for the full text.
