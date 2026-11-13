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

## Explicit invocation (2026-11-13)
- Learner typed: `/skill-contract-reviewer Review /home/user/AI-Engineering/learning-artifacts/agent-skills-first-run/my-first-skill and show the argv, cwd and exit code of check_skill.py.`
- Host found the skill by name and loaded its body. Base directory reported: /root/.claude/skills/skill-contract-reviewer (matches SKILL_ROOT).
- Disclosure: references/contract.md, references/decision-model.md and assets/task-shapes.json were read only after activation.
- Resolved script path: /root/.claude/skills/skill-contract-reviewer/scripts/check_skill.py
- Resolved target path: /home/user/AI-Engineering/learning-artifacts/agent-skills-first-run/my-first-skill
- cwd: /home/user/AI-Engineering/learning-artifacts/agent-skills-first-run
- argv: ["python3", "/root/.claude/skills/skill-contract-reviewer/scripts/check_skill.py", "/home/user/AI-Engineering/learning-artifacts/agent-skills-first-run/my-first-skill"]
- exit code: 0
- Report: {"name": "my-first-skill", "valid": true, "errors": []}
- Selected primitive: Agent Skill (reusable task method with a "when" trigger; no external API, event hook, deterministic transform, or isolated context needed).

## Implicit selection probe
- Pending

## Uninstall
- Pending
