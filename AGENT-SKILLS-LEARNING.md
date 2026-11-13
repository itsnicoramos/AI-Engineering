# My Agent Skills Path
<!-- Managed by the learn-agent-skills tutor.
     Source: learning-paths/agent-skills.json -->

## Route
- Started: 2026-11-12
- Required time: about 9 hours 30 minutes
- Current: 1 of 5

## Prerequisite check
- Files, Python, and command line: Confirmed (python3 3.13.18)
- Node.js and npx: Confirmed (node v22.23.4, npx 10.9.9)
- Selected skill-capable host: Pending
- Install scope: User (~/.claude/skills/)
- Phase 13 Lesson 01 refresher: Pending
- Phase 13 Lesson 05 refresher: Pending
- `tool-poisoning-and-untrusted-instructions`: Pending

## Progress
| Order | Lesson | Status | Evidence | Completed |
|---:|---|---|---|---|
| 1 | 13/22 Portable contract and runtime boundary | In progress | | |
| 2 | 13/24 Discovery and progressive disclosure | Locked | | |
| 3 | 13/25 Invocation and routing | Locked | | |
| 4 | 13/26 Permissions, sandboxes, and trust | Locked | | |
| 5 | 13/27 Evals, packaging, and portability | Locked | | |

## Notes
- Reverse Engineering route requested too; start it after this session with /learn-reverse-engineering.
- Learner wants every artifact and observation pushed to branch learner/agent-skills-progress (PR #1). Workspace: learning-artifacts/agent-skills-first-run/.
- 2026-11-12: Chose user scope so the installed reviewer bundle stays outside the repo; evidence is committed instead.
- 2026-11-13 prediction (13/22): "name is the identifier; description is reusable metadata for the agent to perform." Half right. Correction: description is the routing signal the model reads at selection time ("when to use"), not the procedure ("how", which is the body). Changing it changes which requests activate the skill, so treat it like config code: validate, version, eval.
