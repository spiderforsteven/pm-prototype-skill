<div align="center" style="background:#0B1E19;padding:56px 40px 44px;border-radius:20px;color:#EEECE5;font-family:-apple-system,'Noto Sans SC','PingFang SC',sans-serif;position:relative;overflow:hidden">

<!-- dot texture -->
<div style="position:absolute;inset:0;background-image:radial-gradient(circle at 1px 1px, rgba(238,236,229,.09) 1px, transparent 0);background-size:26px 26px;pointer-events:none"></div>
<!-- glows -->
<div style="position:absolute;top:-80px;left:-60px;width:340px;height:340px;border-radius:50%;background:radial-gradient(circle, rgba(255,180,84,.16), transparent 70%);pointer-events:none"></div>
<div style="position:absolute;bottom:-100px;right:-40px;width:380px;height:380px;border-radius:50%;background:radial-gradient(circle, rgba(92,230,165,.13), transparent 70%);pointer-events:none"></div>

<div style="position:relative">
<p style="font-family:ui-monospace,'JetBrains Mono',monospace;font-size:12px;letter-spacing:.22em;color:rgba(238,236,229,.55);margin:0 0 18px">HERMES AGENT · PRODUCT DESIGN WORKFLOW · v1.0.0</p>

<h1 style="font-family:'Noto Serif SC',serif;font-weight:900;font-size:44px;letter-spacing:-.02em;margin:0 0 10px;color:#EEECE5">PM-Prototype-Skill</h1>

<p style="font-size:17px;line-height:1.7;color:rgba(238,236,229,.82);max-width:620px;margin:0 auto 22px">An interactive prototype design skill for Hermes Agent that <b style="color:#5CE6A5">forces multi-round clarification before any design work</b> — built for product managers who ship UI through AI.</p>

<div style="display:flex;gap:10px;justify-content:center;flex-wrap:wrap;margin-bottom:26px">
<span style="font-size:12px;padding:6px 14px;border:1px solid rgba(255,180,84,.5);color:#FFB454;border-radius:999px;letter-spacing:.04em">CLARIFY FIRST</span>
<span style="font-size:12px;padding:6px 14px;border:1px solid rgba(92,230,165,.5);color:#5CE6A5;border-radius:999px;letter-spacing:.04em">DESIGN SECOND</span>
<span style="font-size:12px;padding:6px 14px;border:1px solid rgba(125,185,255,.5);color:#7DB9FF;border-radius:999px;letter-spacing:.04em">TOKEN-DRIVEN</span>
</div>

<p style="font-size:14px;color:rgba(238,236,229,.5);margin:0;font-family:ui-monospace,'JetBrains Mono',monospace">github.com/spiderforsteven/pm-prototype-skill</p>
</div>
</div>

<div style="font-family:-apple-system,'Noto Sans SC','PingFang SC',sans-serif;max-width:860px;margin:0 auto;padding:8px 8px 0;color:#1E1E1E">

## Why this exists

LLM-driven prototype work fails most often at the **understanding** stage, not the rendering stage. Real incidents that shaped this skill:

| Incident | What went wrong |
|---|---|
| A mode-switch card looked like a plain settings row | The agent didn't realize "Smart care" was the entry to 4 planting strategies |
| A manual mode was nested inside Device Settings | Misread as a sibling mode instead of a hidden advanced mode |
| Device telemetry mixed into the mode card | Water level, light state are **objective state** — they should be an independent always-visible block, not mode attributes |
| Two names for one concept | "AI mode" vs "Smart care" on the same screen = cognitive load |

The fix, encoded as a mandatory protocol: **restate → clarify → confirm → design**.

---

## The 5-step workflow

<div style="display:flex;gap:12px;flex-wrap:wrap;margin:20px 0">

<div style="flex:1;min-width:140px;border:1px solid #E4E1DA;border-radius:14px;padding:18px 16px;background:#FDFCFA">
<div style="font-family:ui-monospace,monospace;font-size:22px;font-weight:700;color:#B9791E">01</div>
<div style="font-weight:700;font-size:14px;margin:6px 0 4px">Restate</div>
<div style="font-size:12.5px;color:#5E6B64;line-height:1.55">Output page structure + interaction points + a list of open questions. Never skip.</div>
</div>

<div style="flex:1;min-width:140px;border:1px solid #E4E1DA;border-radius:14px;padding:18px 16px;background:#FDFCFA">
<div style="font-family:ui-monospace,monospace;font-size:22px;font-weight:700;color:#B9791E">02</div>
<div style="font-weight:700;font-size:14px;margin:6px 0 4px">Clarify</div>
<div style="font-size:12.5px;color:#5E6B64;line-height:1.55">One question at a time. Driven by a 60+ question bank plus four questioning philosophies.</div>
</div>

<div style="flex:1;min-width:140px;border:1px solid #E4E1DA;border-radius:14px;padding:18px 16px;background:#FDFCFA">
<div style="font-family:ui-monospace,monospace;font-size:22px;font-weight:700;color:#B9791E">03</div>
<div style="font-weight:700;font-size:14px;margin:6px 0 4px">Confirm</div>
<div style="font-size:12.5px;color:#5E6B64;line-height:1.55">The PM confirms the final understanding. No confirmation, no design.</div>
</div>

<div style="flex:1;min-width:140px;border:1px solid #E4E1DA;border-radius:14px;padding:18px 16px;background:#FDFCFA">
<div style="font-family:ui-monospace,monospace;font-size:22px;font-weight:700;color:#B9791E">04</div>
<div style="font-weight:700;font-size:14px;margin:6px 0 4px">Design</div>
<div style="font-size:12.5px;color:#5E6B64;line-height:1.55">Load the brand design-token system, then ship wireframe / hi-fi / review report.</div>
</div>

<div style="flex:1;min-width:140px;border:1px solid #E4E1DA;border-radius:14px;padding:18px 16px;background:#FDFCFA">
<div style="font-family:ui-monospace,monospace;font-size:22px;font-weight:700;color:#B9791E">05</div>
<div style="font-weight:700;font-size:14px;margin:6px 0 4px">Deliver</div>
<div style="font-size:12.5px;color:#5E6B64;line-height:1.55">Editable wireframes or deployable interactive HTML. Verified in both themes.</div>
</div>

</div>

---

## Questioning philosophy

The question bank is raw material. Four philosophies make questioning exhaustive:

<div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;margin:18px 0">

<div style="border-left:3px solid #FFB454;border-radius:10px;padding:14px 16px;background:#FFF9F0">
<div style="font-weight:700;font-size:14px">Socratic probing</div>
<div style="font-size:12.5px;color:#5E6B64;line-height:1.6;margin-top:4px">Derive hidden assumptions from answers. <i>"You want telemetry independent because switching modes shouldn't hide the water level?"</i></div>
</div>

<div style="border-left:3px solid #5CE6A5;border-radius:10px;padding:14px 16px;background:#F2FCF6">
<div style="font-weight:700;font-size:14px">Adversarial review</div>
<div style="font-size:12.5px;color:#5E6B64;line-height:1.6;margin-top:4px">Find the flaws on the user's behalf. <i>"Could a brand-new user find this entry point?"</i></div>
</div>

<div style="border-left:3px solid #7DB9FF;border-radius:10px;padding:14px 16px;background:#F3F8FF">
<div style="font-weight:700;font-size:14px">Breakpoint scan</div>
<div style="font-size:12.5px;color:#5E6B64;line-height:1.6;margin-top:4px">Walk the task path step by step looking for stalls: can't find entry, can't see state, can't undo.</div>
</div>

<div style="border-left:3px solid #B98A2E;border-radius:10px;padding:14px 16px;background:#FBF7EF">
<div style="font-weight:700;font-size:14px">Friendliness check</div>
<div style="font-size:12.5px;color:#5E6B64;line-height:1.6;margin-top:4px">Undo, mis-tap protection, feedback within 100ms, naming consistency, progressive disclosure.</div>
</div>

</div>

Grounded in Nielsen's 10 usability heuristics, Hick's law, Fitts's law, and mental-model design.

---

## Repository layout

```
├── SKILL.md                      # The working protocol (Hermes skill format)
├── references/
│   └── 问题库全表.md             # Full question bank: 60+ questions across A-F scenarios,
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

---

<p align="center" style="color:#8A948E;font-size:13px;margin:32px 0 8px">PM-Prototype-Skill · built for product managers who ship UI through AI · MIT License</p>

</div>
