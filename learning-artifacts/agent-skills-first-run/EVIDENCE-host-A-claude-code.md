# Lesson 13/22 evidence: host A (Claude Code, cloud session)

## Install (2026-11-13)
- cwd: /home/user/AI-Engineering/learning-artifacts/agent-skills-first-run (TARGET_ROOT)
- argv: npx -y skills add rohitg00/ai-engineering-from-scratch --skill skill-contract-reviewer --full-depth -g -a claude-code -y
- exit code: 0
- Installer report: found 28 skills, selected 1 (skill-contract-reviewer), copied to ~/.claude/skills/skill-contract-reviewer
- Note: the summary also named ~/.agents/skills/skill-contract-reviewer as the canonical path, but that directory does not exist after install. Mode was "copied", not symlinked.
- SKILL_ROOT=/root/.claude/skills/skill-contract-reviewer (pwd -P); `test -f "$SKILL_ROOT/SKILL.md"` exit 0
- Bundle files: SKILL.md, assets/task-shapes.json, references/contract.md, references/decision-model.md, scripts/check_skill.py

## Discovery
- Observed: right after the install, with no restart or rescan, the host added `skill-contract-reviewer` to the session's skill catalog. Description shown: "Validate an Agent Skill package and choose the right instruction, capability, or lifecycle primitive before implementation."
- So this host picks up new user-scope skills mid-session. Only name and description entered the catalog; the body had not been loaded.

## Explicit invocation
- Pending

## Implicit selection probe
- Pending

## Uninstall
- Pending
