# PM-Prototype-Skill

**Interactive prototype design skill for Hermes Agent, built for product managers.**

A working protocol that forces **multi-round clarification BEFORE any design work**: when a PM shares a design file (via MCP), a screenshot, or a plain optimization request, the agent must first restate its understanding, then ask one question at a time to nail down interaction details, and only then produce design deliverables backed by a design-token system.

> Core rule: **Never design before you understand.** Better to ask three more rounds than ship one wrong version.

## Why this exists

LLM-driven prototype work fails most often at the *understanding* stage, not the *rendering* stage. Real incidents that shaped this skill:

- A mode-switch card (Smart care) looked like a plain settings row — the agent didn't realize it was the entry to 4 planting strategies.
- A "Manual mode" was nested inside Device Settings, not a sibling mode — misread as a flat toggle.
- Device telemetry (water tank level, light state) was mixed into the mode card, when it should be an **independent always-visible status block**.
- Two names for the same concept on one screen (AI mode vs Smart care).

This skill encodes the fix: **restate → clarify → confirm → design**.

## The 5-step workflow

```
Input (MCP design file / screenshot / text request)
  ↓
① Restate understanding   — page structure + interaction points + open questions
  ↓
② Clarify one question at a time   — built-in question bank + questioning philosophy
  ↓
③ Confirm consensus   — only after the PM confirms may design begin
  ↓
④ Execute design   — load design tokens → wireframe / hi-fi prototype / review report
  ↓
⑤ Deliver   — deployable HTML or editable wireframe
```

## Questioning philosophy

The question bank (see `references/问题库全表.md`) is raw material. Four philosophies make questioning exhaustive:

1. **Socratic probing** — derive hidden assumptions from answers ("You want X because Y?").
2. **Adversarial review** — find the flaws on the user's behalf ("Could a brand-new user find this entry point?").
3. **Interaction breakpoint scan** — walk the task path step by step looking for stalls (can't find entry / can't see state / can't undo).
4. **Friendliness check** — undo, mis-tap protection, feedback within 100ms, naming consistency, progressive disclosure.

Grounded in Nielsen's 10 usability heuristics, Hick's law, Fitts's law, and mental-model design.

## Repository layout

```
├── SKILL.md                      # The working protocol (Hermes skill format)
├── references/
│   └── 问题库全表.md             # Full question bank: 60+ questions, A-F scenarios,
│                                 # adversarial checklist, breakpoint scan, Socratic templates
├── docs/
│   └── 使用说明.md               # Distributable usage guide (Chinese) with placeholder table
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
