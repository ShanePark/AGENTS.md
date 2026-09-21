## Implementation

- Read applicable instructions and relevant code, tests, and documentation before editing. Use the repository's existing tooling and commands.
- Resolve questions from the repository first. Ask the user before proceeding when a remaining ambiguity materially affects scope, behavior, interfaces, or acceptance criteria.
- Make the smallest, simplest change that fully satisfies the request. Do not invent requirements or add unrelated changes, speculative abstractions, or unnecessary dependencies.
- Follow existing conventions and preserve unrelated behavior. Comment only non-obvious rationale, invariants, or constraints.
- Check unfamiliar APIs against installed code or version-matched official documentation rather than guessing.
- Reproduce bugs before fixing them when practical. Add or update focused tests as needed to cover changed behavior, and keep affected documentation accurate.

## Delegation and Parallel Work

- When subagents are available, the main agent focuses on planning, delegation, coordination, and user communication; delegate substantial exploration, implementation, and verification by default.
- The main agent handles brief tasks, work requiring its broader context, and work that cannot be delegated with the available tools.
- Parallelize independent work, including planning and design when useful.
- Use the tool's default subagent model for routine work; use the same model as the main agent for work requiring substantial reasoning, such as complex planning or design.
- Give each delegated task one owner, a clear scope, relevant context and constraints, dependencies, deliverables, and verification criteria.
- Keep concurrent writes separate. Assign one owner to each shared file, mutable resource, or cross-cutting contract.
- Only the main agent may control shared desktop or browser sessions (computer use). Subagents may run isolated headless browser tests without accessing shared sessions.
- The main agent integrates results, resolves conflicts, and reviews the final diff and verification evidence before reporting completion.

## Verification and Completion

- Run the project's relevant checks, starting with focused checks and expanding based on risk and blast radius.
- Review the final diff against the request for correctness, regressions, and unnecessary changes. Fix confirmed in-scope issues, then repeat review and affected checks.
- Never weaken or bypass tests or checks merely to make a change pass.
- Report what changed, checks performed and results, anything not verified and why, and remaining risks or assumptions. Do not label failures pre-existing without evidence.
- Do not claim completion without relevant verification or present unperformed checks as passed.

## Git and Workspace Safety

- Inspect the working tree and relevant diffs before editing and before Git write operations.
- Perform Git write operations (such as staging, committing, branching, pushing, or merging) only when requested by the user. Read-only inspection is allowed.
- Preserve pre-existing and concurrent work. Stage and commit only task-owned changes, using individual hunks in files with unrelated edits; never discard, overwrite, or stash unrelated changes.
- Do not expose secrets or credentials in code, logs, commits, or reports.
- Clean up temporary files and processes you created, without disturbing existing sessions or services.
