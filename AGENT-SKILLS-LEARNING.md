# My Agent Skills Path
<!-- Managed by the learn-agent-skills tutor.
     Source: learning-paths/agent-skills.json -->

## Route
- Started: 2026-11-12
- Required time: about 9 hours 30 minutes
- Current: 2 of 5

## Prerequisite check
- Files, Python, and command line: Confirmed (python3 3.13.18)
- Node.js and npx: Confirmed (node v22.23.4, npx 10.9.9)
- Selected skill-capable host: A) Claude Code (this cloud session), primary; B) learner's local host (name Pending), second run
- Install scope: User (~/.claude/skills/)
- Phase 13 Lesson 01 refresher: Pending
- Phase 13 Lesson 05 refresher: Pending
- `tool-poisoning-and-untrusted-instructions`: Pending

## Progress
| Order | Lesson | Status | Evidence | Completed |
|---:|---|---|---|---|
| 1 | 13/22 Portable contract and runtime boundary | Done | Host A (Claude Code): install exit 0, hot-reload discovery, explicit run of check_skill.py exit 0 valid, implicit probe selected but unverified, uninstall verified ("Unknown skill"). See learning-artifacts/agent-skills-first-run/EVIDENCE-host-A-claude-code.md. Quiz 2/6, retake 6/6 | 2026-11-13 |
| 2 | 13/24 Discovery and progressive disclosure | In progress | | |
| 3 | 13/25 Invocation and routing | Locked | | |
| 4 | 13/26 Permissions, sandboxes, and trust | Locked | | |
| 5 | 13/27 Evals, packaging, and portability | Locked | | |

## Notes
- Reverse Engineering route requested too; start it after this session with /learn-reverse-engineering.
- Learner wants every artifact and observation pushed to branch learner/agent-skills-progress (PR #1). Workspace: learning-artifacts/agent-skills-first-run/.
- 2026-11-12: Chose user scope so the installed reviewer bundle stays outside the repo; evidence is committed instead.
- 2026-11-13 prediction (13/22): "name is the identifier; description is reusable metadata for the agent to perform." Half right. Correction: description is the routing signal the model reads at selection time ("when to use"), not the procedure ("how", which is the body). Changing it changes which requests activate the skill, so treat it like config code: validate, version, eval.
- 2026-11-13: Host plan: run the full 13/22 lab in Claude Code (this session) first, then repeat on the learner's local host. That second run also prepares the two-host portability check in 13/27.
- 2026-11-13: TARGET_ROOT=/home/user/AI-Engineering/learning-artifacts/agent-skills-first-run (empty before start: ls -A count 0). Created my-first-skill/SKILL.md; `test -f` exit 0.
- 2026-11-13: 13/22 quiz 2/6. Missed Q1 (skill + MCP), Q3 (host extension vs portable core), Q4 (hook = event timing), Q5 (AGENTS.md = repo-wide defaults; picked the skill case). Got Q2 (name matches directory) and Q6 (a skill grants procedure, not permission).
- Weak spot: choosing a primitive by responsibility. Keyword table: event -> hook; reusable method -> skill; external API -> MCP tool; repo conventions -> AGENTS.md; deterministic -> code; isolated context -> subagent; one-off -> prompt.
- Clarified a misconception: explicit vs implicit is about who picks the skill (user names it vs model matches description), not what the skill does. skill-contract-reviewer is a package validator, not a security auditor.
- Pending: host B (learner's local host) repeat of the 13/22 lab, plus a clean implicit-routing probe in a fresh session.
- 2026-11-13: 13/22 quiz retake with shuffled options: 6/6. Same items as the first attempt, so this shows recall; the SQL quick check in the review queue tests transfer.
- 2026-11-13: Transfer check passed. SQL scenario: "implicit; description, since the LLM needs to decide whether to activate the skill." Cleared from the review queue.
- 2026-11-13 prediction (13/24): same-name collision. "Workspace wins since maintainers own it, but it can shadow mine." Correct policy and risk. Added: the workspace is writable by anyone who lands a commit or ships a cloned repo, so shadowed candidates must stay visible in diagnostics.
- 2026-11-13 lab (13/24): `python3 code/main.py` in the lesson dir, exit 0 (project beats user for evidence-report; L1 357 / L2 70 / L3 46 chars). `python3 -m unittest discover -s code/tests -v`: 23 tests OK. Doc mismatch: docs say the demo attempts a traversal escape, but the demo prints none; tests cover it (test_rejects_traversal_reference).
- 2026-11-13 checkpoint (13/24): learner wrote the branch line "If the user asks for an ADR, read references/adr-format.md". Trace learning-artifacts/agent-skills-first-run/trace_13_24.py (output in trace_13_24.out.json), exit 0. Discovery: 1 candidate per scope. Catalog: project-first precedence lets an untrusted shadow copy win; user-first keeps mine; the loser is always in collisions. Activation: body 249 chars. Disclosure: the plain request loads no reference; the ADR request loads references/adr-format.md (155 chars, with a reason). Containment: `references/../../...` and `/etc/passwd` both rejected. Edited skill still valid (check_skill.py exit 0).

## Review queue
- 13/22 primitive selection (first attempt missed Q1, Q3, Q4, Q5; retake 6/6). Revisit in 13/25 routing evals.
