<p align="center">
  <img src="assets/hero.png" alt="PM-Prototype-Skill" width="100%" />
</p>

<div align="center">

![version](https://img.shields.io/badge/version-v1.0.0-0B1E19?style=flat-square)
![license](https://img.shields.io/badge/license-MIT-5CE6A5?style=flat-square)
![platform](https://img.shields.io/badge/platform-Hermes%20Agent-FFB454?style=flat-square)
![lang](https://img.shields.io/badge/docs-EN%20%2B%20ZH-7DB9FF?style=flat-square)

</div>

---

## Why this exists

LLM-driven prototype work fails most often at the **understanding** stage, not the rendering stage. Real incidents that shaped this skill:

| Incident | What went wrong |
|---|---|
| A mode-switch card looked like a plain settings row | The agent didn't realize "Smart care" was the entry to 4 planting strategies |
| A manual mode was nested inside Device Settings | Misread as a sibling mode instead of a hidden advanced mode |
| Device telemetry mixed into the mode card | Water level, light state are **objective state** — they should be an independent always-visible block, not mode attributes |
| Two names for one concept | "AI mode" vs "Smart care" on the same screen = cognitive load |

The fix, encoded as a mandatory protocol: **restate → clarify → confirm → design**.

## The 5-step workflow

| Step | Name | What happens |
|---|---|---|
| 01 | **Restate** | Output page structure + interaction points + a list of open questions. Never skipped. |
| 02 | **Clarify** | One question at a time, driven by a 60+ question bank plus four questioning philosophies. |
| 03 | **Confirm** | The PM confirms the final understanding. No confirmation, no design. |
| 04 | **Design** | Load the brand design-token system, then ship wireframe / hi-fi / review report. |
| 05 | **Deliver** | Editable wireframes or deployable interactive HTML, verified in both themes. |

## Questioning philosophy

The question bank is raw material. Four philosophies make questioning exhaustive:

- **Socratic probing** — derive hidden assumptions from answers. *"You want telemetry independent because switching modes shouldn't hide the water level?"*
- **Adversarial review** — find the flaws on the user's behalf. *"Could a brand-new user find this entry point?"*
- **Breakpoint scan** — walk the task path step by step looking for stalls: can't find entry, can't see state, can't undo.
- **Friendliness check** — undo, mis-tap protection, feedback within 100ms, naming consistency, progressive disclosure.

Grounded in Nielsen's 10 usability heuristics, Hick's law, Fitts's law, and mental-model design.

## Repository layout

```
├── SKILL.md                      # The working protocol (Hermes skill format)
├── references/
│   └── 问题库全表.md             # Full question bank: 60+ questions across A-F scenarios,
│                                 # adversarial checklist, breakpoint scan, Socratic templates
├── docs/
│   └── 使用说明.md               # Distributable usage guide (Chinese) with placeholder table
├── assets/
│   └── hero.png                  # README banner
└── README.md
```

## Install (Hermes Agent)

```bash
cp -r pm-prototype-skill ~/.hermes/skills/product-management/
hermes skills list | grep prototype
```

Companion skills: `maygrove-design-system` (design tokens), `mastergo-mcp-handoff` (read MasterGo design files via MCP), `maygrove-wireframe` (editable wireframes).

## Usage example

> "Here's a MasterGo link — I want to improve the mode-switching interaction, deliver a hi-fi prototype."

The agent will: read the design DSL via MCP → restate the page structure → ask one clarifying question at a time (mode hierarchy? does telemetry change with mode? how discoverable must the entry be?) → confirm → load design tokens → ship an interactive HTML prototype.

## License

MIT
