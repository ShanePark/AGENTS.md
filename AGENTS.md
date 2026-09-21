# Working Agreements

Shared defaults for coding tasks. Use project instructions for repository-specific commands and conventions.

## Implementation

- Read applicable instructions and relevant code and tests before editing.
- Resolve questions from the repository first. Ask the user before proceeding when a remaining ambiguity materially affects scope, behavior, interfaces, or acceptance criteria.
- Make the smallest, simplest change that fully satisfies the request. Do not invent requirements or add unrelated changes, speculative abstractions, or unnecessary dependencies.
- Follow existing conventions and preserve unrelated behavior. Comment only non-obvious rationale, invariants, or constraints.
- Add or update focused tests for behavior changes; reproduce bugs before fixing them when practical.

## Delegation and Parallel Work

- When subagents are available, the main agent focuses on planning, delegation, coordination, and user communication; delegate substantial exploration, implementation, and verification by default.
- The main agent handles brief tasks, work requiring its broader context, and work that cannot be delegated with the available tools.
- Parallelize independent work, including planning and design when useful.
- Use the tool's default subagent model for routine work; use the same model as the main agent for work requiring substantial reasoning, such as complex planning or design.
- Give each delegated task one owner, a clear scope, relevant context and constraints, dependencies, deliverables, and verification criteria.
- Keep concurrent writes separate. Assign one owner to each shared file, mutable resource, or cross-cutting contract.
- Only the main agent may control shared desktop or browser sessions (computer use). Subagents may run isolated headless browser tests without accessing shared sessions.
- The main agent integrates results, resolves conflicts, and reviews the final diff and verification evidence before reporting completion.

## Completion

- Run the project's relevant checks, starting with focused checks and expanding based on risk and blast radius.
- Never weaken or bypass tests or checks merely to make a change pass.
- Report what changed, checks and results, anything not verified and why, and remaining risks or assumptions. Distinguish pre-existing failures from failures introduced by the change.
- Do not claim completion without relevant verification or present unperformed checks as passed.

## Git

- Inspect the working tree and relevant diffs before editing and before Git write operations.
- Perform Git write operations (such as staging, committing, branching, or pushing) only when requested by the user. Read-only inspection is allowed.
- Treat pre-existing changes as user-owned. Never discard, overwrite, stage, or commit unrelated work; stage and commit only changes made for the current task.
- Never commit secrets or credentials.
