# AGENTS.md

This repository contains one portable Agent Skill named `engineering-han`.

- Keep `SKILL.md` concise and use it to route task-specific guidance from `references/`.
- Preserve the single public skill name `engineering-han`; do not split its modes into separately installed skills without an explicit design decision.
- Keep cross-project workflow here and leave stack-, product-, and repository-specific facts in each target project's local instructions.
- Add a rule only when observed use shows that it changes decisions across projects. Avoid accumulating one-off failures or generic coding advice.
- Prefer outcome and decision criteria over rigid phases. Reserve mandatory steps for safety, permissions, data integrity, or reliable verification.
- Validate the skill with the bundled Skill Creator `quick_validate.py` after changing its metadata or structure.
