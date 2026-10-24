---
name: gongzi-teaches-code-help
description: >
  【速查卡】一次性列出 ponytail 全部模式、技能和命令的一句话说明，
  以及如何切换强度、如何关闭、如何更新。忘了怎么用就说 ponytail help。
  触发词：/ponytail-help、ponytail 怎么用、ponytail 有哪些命令。
---

# Ponytail Help

Display this reference card when invoked. One-shot, do NOT change mode,
write flag files, or persist anything.

## Levels

| Level | Trigger | What change |
|-------|---------|-------------|
| **Lite** | `/ponytail lite` | Build what's asked, name the lazier alternative in one line. |
| **Full** | `/ponytail` | The ladder enforced: YAGNI → stdlib → native → one line → minimum. Default. |
| **Ultra** | `/ponytail ultra` | YAGNI extremist. Deletion before addition. Challenges requirements before building. |

Level sticks until changed or session end.

## Skills

| Skill | Trigger | What it does |
|-------|---------|--------------|
| **ponytail** | `/ponytail` | Lazy mode itself. Simplest solution that works. |
| **ponytail-review** | `/ponytail-review` | Over-engineering review: `L42: yagni: factory, one product. Inline.` |
| **ponytail-audit** | `/ponytail-audit` | Whole-repo over-engineering audit: ranked list of what to delete. |
| **ponytail-debt** | `/ponytail-debt` | Harvest `ponytail:` shortcut comments into a tracked ledger. |
| **ponytail-gain** | `/ponytail-gain` | Measured-impact scoreboard: less code, less cost, more speed. |
| **ponytail-help** | `/ponytail-help` | This card. |

Codex uses `@ponytail`, `@ponytail-review`, and `@ponytail-help`; Claude Code
and OpenCode use the slash-command forms above (OpenCode ships all six as
slash commands).

## Deactivate

Say "stop ponytail" or "normal mode". Resume anytime with `/ponytail`.
`/ponytail off` also works.

## Configure Default Mode

Default mode = `full`, auto-active every session. Change it:

**Environment variable** (highest priority):
```bash
export PONYTAIL_DEFAULT_MODE=ultra
```

**Config file** (`~/.config/ponytail/config.json`, Windows: `%APPDATA%\ponytail\config.json`):
```json
{ "defaultMode": "lite" }
```

Set `"off"` to disable auto-activation on session start, activate manually
with `/ponytail` when wanted.

Resolution: env var > config file > `full`.

## Update

Enable auto-update once: open `/plugin`, go to Marketplaces, pick ponytail, Enable auto-update. Claude Code then pulls new versions at startup (run `/reload-plugins` when it prompts). Manual refresh: `/plugin marketplace update ponytail` then `/reload-plugins`.

If `/plugin` is not recognized, your Claude Code is out of date. Update it (`npm install -g @anthropic-ai/claude-code@latest`, or `brew upgrade claude-code`) and restart. Other hosts use their own update flow.

## More

Full docs + examples: https://github.com/DietrichGebert/ponytail

---

## 来源

本项目基于 [Ponytail](https://github.com/DietrichGebert/ponytail)（MIT License，作者 DietrichGebert）改写，
保留了原作者的版权声明（见 `LICENSE`）。核心思路一致，表述与结构按中文语境重写。

触发词：怎么用、有哪些命令、速查
