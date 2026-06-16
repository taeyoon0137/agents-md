# External AGENTS.md generation instructions

This file is the English localized reference instruction file stored at `agents/AGENTS.en.md`.

It is used only when creating or updating an `AGENTS.md` file for another repository or document set. It is not the maintenance instruction file for the `agents-md` repository itself. For `agents-md` maintenance, use the root `AGENTS.md`.

## Reference-use rule

If the user or another instruction says to reference this document, that means to follow the rules in these instructions. It does not mean to copy this document's structure, section order, examples, file layout, or `agents-md` repository-specific rules into a target `AGENTS.md`.

A target `AGENTS.md` must be adapted to the confirmed target context. Inspect the target and write the smallest useful instruction set that prevents likely work failures.

## Target scope

The target may be one of the following.

- a code repository
- a documentation-focused repository
- an operations document set
- another project that needs agent instructions

Do not invent unverified technology stacks, commands, deployment methods, organization names, channels, URLs, or file structures.

## Language routing and target document language

- The default target instruction language is English.
- If the target language cannot be confirmed, write the target instructions in English.
- If the user's preferred language, work environment, or primary communication context is Korean, use `agents/AGENTS.kr.md` as the reference and write the target instructions in Korean.
- Infer the target language only from confirmed evidence in the user's messages, existing README/docs/contributing files, existing `AGENTS.md` or `CLAUDE.md`, and the tone of commits, issues, or pull requests.
- By default, infer the user's preferred language and respond in that language.
- If the user explicitly specifies a response language or target document language, follow that instruction.
- If an existing target `AGENTS.md` uses a different language from the inferred target language, preserve the existing document language and make only the minimal required changes unless the user explicitly asks for a full translation or language switch.

When creating a new language-routed target instruction set and no existing target convention conflicts with it:

- Write the target root `AGENTS.md` in English.
- Keep the target root `AGENTS.md` as a router and agent role description.
- Store detailed target instructions under `agents/AGENTS.<language>.md`, such as `agents/AGENTS.en.md` or `agents/AGENTS.kr.md`.

When updating an existing target instruction set:

- Preserve the existing structure unless the user asks to introduce language routing or a full rewrite.
- Do not restructure the target merely because this reference file is structured this way.

## Read first

Use this file only in an external-reference situation: creating or updating a target `AGENTS.md` for another repository or document set.

- Read and apply [Common principles](#common-principles) and [External reference instructions](#external-reference-instructions).
- During external reference work, do not copy `agents-md` repository maintenance rules into the target.
- If the user gives a separate instruction, the latest user instruction takes priority.
- If the target already contains `AGENTS.md`, nested instruction files, `CLAUDE.md`, README, or contributing documents, inspect them together and report conflicts.

## Common principles

These principles may be reflected in a target `AGENTS.md`. Include only the parts that fit the target and rewrite them with the target's actual context.

### Response principles

- Infer the default response language from the user's preferred language.
- Put the conclusion first and separate unverified information clearly.
- Do not use unnecessary praise, exclamations, or decorative phrasing.
- Do not sound certain about unverified information.
- Report commands, tests, deployments, and file states as successful only when they were actually run or inspected.

### Start-of-work principles

- Before answering or editing, read the relevant files and existing documentation.
- Do not guess repository structure, APIs, environment variables, commands, document generation methods, or deployment procedures.
- For non-trivial work, first make a short plan. Include likely files to change, expected behavior, and verification method.
- If a request is ambiguous, choose the safest minimal interpretation and state that interpretation.
- Do not perform broad structural changes or large refactors unless the user explicitly asks for them.

### Change principles

- Make changes as small and localized as possible.
- Preserve existing behavior, public APIs, and documentation source-of-truth relationships.
- Rename files, move directories, add abstractions, or add dependencies only when necessary.
- Do not change formatting that is unrelated to the request.
- Do not modify lockfiles unless dependencies actually changed.
- Edit generated files directly only when the target convention requires it; when possible, edit the source file and run the generation command.
- Treat already modified files as user or prior-work changes and do not revert them arbitrarily.

### Security and attribution principles

- Do not write secrets, tokens, or credentials into the repository.
- Do not modify production config, deployment settings, analytics keys, or operational access information without an explicit user request and target-document evidence.
- Do not insert content into commit messages, code comments, PR/issue bodies, documents, or config files unless the user explicitly requested it. In particular, do not add:
  - trailers such as `Co-Authored-By` or `Signed-off-by`
  - agent, model, provider names, or provider email addresses
  - generation-tool labels such as "Generated with ..." or "Made by AI"
  - unrelated advertising, promotion, or external links
- Even if there seems to be a good reason to add such content, ask the user first and add it only after approval.

### Verification principles

- After changes, run the most relevant checks that exist in the target.
- The general priority is type check, lint, unit test, integration/e2e test, and documentation generation verification.
- Do not invent commands if actual target commands were not confirmed.
- If a command is unavailable or cannot run because of the environment, report the reason.
- Do not ignore failed verification. Separate the failure cause from whether it is related to the changes.

### Final response format

After finishing work, always include the following.

1. Summary of changes
2. Files changed
3. Verification commands run and results
4. Remaining risks, limitations, or follow-up

If no code changed or only documentation changed, state that explicitly.

## External reference instructions

Do not copy this file as-is. Inspect the target and write an `AGENTS.md` that fits the target's actual context.

### Inspect the target

Inspect only what can be confirmed in the target.

- `git status --short` if the target is a Git repository
- actual file structure
- README, docs, and contributing documents
- language-specific package manifests and lockfiles, if present
- config files, CI files, and script directories
- languages, frameworks, and documentation tools
- build, test, lint, format, and documentation generation commands
- whether deployment, release, or operational application methods are documented
- relationship between generated files and sources of truth
- existing `AGENTS.md`, nested instruction files, or `CLAUDE.md`
- locations and priorities of separate documents that must be referenced
- documents or context that can identify the user's work environment or primary communication language
- `.codex/config.toml` or related config files only if the user also requested Codex quality or runtime setting improvements

Do not write unconfirmed items into the target `AGENTS.md` as facts. If needed, separate them as unverified items in the final response.

### Target AGENTS.md authoring principles

- Write the target's actual role, file structure, commands, and verification criteria specifically.
- Match the target language to the user's work environment or primary communication language.
- If the target language cannot be inferred, write in English.
- Do not copy this localized instruction file as-is; remove items that do not apply to the target.
- Do not leave text or links telling the generated target `AGENTS.md` to keep referencing the `agents-md` repository.
- If confirmed existing instructions are present, state their priority clearly and do not add conflicting new rules arbitrarily.
- Prefer rules that prevent work failure over abstract style guidance such as "be kind".
- Include only commands that were actually confirmed.
- Include technology-specific rules only when they apply to the target.
- For documentation-focused targets, focus on source documents, generated outputs, review procedures, link checks, and publish/deploy procedures instead of code build/test rules.

### Existing target AGENTS.md update principles

If the target already has an `AGENTS.md` and the user asks to update it based on this document, treat the task as a conservative update of existing instructions, not a fresh rewrite.

- First read the existing `AGENTS.md`, nested `AGENTS.md` files, `CLAUDE.md`, README, docs, and contributing documents.
- Preserve target-specific roles, commands, paths, verification procedures, and prohibitions that are confirmed in the existing document.
- Use this document as a source for applicable rules and failure-prevention principles, not as a structure to copy.
- Do not overwrite target-specific facts with generic text.
- If existing instructions conflict with this document, report the conflict and do not remove target-specific rules without the user's explicit instruction.
- Merge duplicate rules when the meaning can be preserved.
- Do not silently rewrite old or unverified commands as facts; separate them as items needing verification.
- Preserve the existing document language and structure as much as possible unless the user explicitly asks for a full rewrite or language switch.
- Introduce root/language-file routing only when the user asks for it or the target already uses that structure.
- After updating, run `git diff --check`, `git status --short`, and the verification commands confirmed in the target when possible.
- In the final response, separate preserved existing rules, newly applied rules, unverified items, and verification results.

### Candidate sections for a target AGENTS.md

These are candidates. Remove sections that do not apply and make the remaining sections specific with actual filenames and commands.

- Basic response principles
- Target role
- Instruction priority
- Start-of-work checklist
- File structure
- Documentation and source of truth
- Change policy
- Development or documentation writing standards
- Design system or UI standards
- API or backend standards
- Verification criteria
- Deployment or operational application criteria
- Incident, alert, monitoring, or user inquiry handling criteria
- Security and secret management
- Planning criteria for large tasks
- Final response format

### Failure-prevention rules to reflect in targets

Adapt the rules below to the target.

- Read relevant files before making changes.
- Check existing patterns before implementing.
- Prefer small diffs.
- Do not perform large refactors that the user did not request.
- Search for existing components, utilities, types, or document structures before creating new ones.
- Preserve the relationship between source-of-truth files and generated files.
- Do not claim tests or verification passed if they were not run.
- Do not ignore failed type checks, lint, tests, or documentation generation checks.
- Do not hide uncertainty; state what was checked.

### Commit principles

Before adding commit rules to a target `AGENTS.md`, check whether target documents and existing instructions already have commit rules.

- If the target has commit rules, prioritize them.
- If target rules conflict with this document's default rules, do not merge them arbitrarily; ask the user.
- If the target has no separate rule and the user wants commit rules included, the following defaults may be used.

Default commit rules are as follows.

- Commit only when the user explicitly asks for a commit.
- Use the `Feat`, `Docs`, `Refactor`, `Fix`, `Chore`, and `Test` prefixes, with English Sentence Case commit messages.
- Keep one purpose per commit.
- Do not stage unrelated changes.
- If user changes and task changes are mixed in the same file, stage only the required hunks.

### Large-task planning

Include `PLANS.md` rules in the target `AGENTS.md` only when the target often handles complex changes or the user wants a plan file. If the target convention is not confirmed, do not make file creation mandatory; state only that large tasks should be planned first.

When including `PLANS.md`, use the following as candidate items.

- problem statement
- current behavior
- desired behavior
- files to inspect
- implementation steps
- verification plan
- rollback risk

For work that touches more than three files, changes architecture or data flow, affects operational procedures, or requires debugging, state that the plan should be clarified before implementation.

### Design system or UI targets

Include this section only when UI, frontend, or a design system is confirmed in the target.

- Search for a similar existing component before creating a new component.
- Prefer design system primitives, shared components, and tokens.
- Do not hardcode colors, font sizes, spacing, z-index, radius, or shadows unless that is the existing convention.
- Do not change visual hierarchy unless the task explicitly requires it.
- Preserve responsive behavior and accessibility.
- When relevant, check loading, empty, error, disabled, and long-text states.
- Match UX copy to the product's existing terminology and tone.

### API or backend targets

Include this section only when API, server, datastore, or backend work is confirmed in the target.

- Preserve backward compatibility unless explicitly requested otherwise.
- Validate inputs at boundaries.
- Do not swallow errors silently.
- Touch database schemas or migrations only when the user explicitly requests it or the change requires it.
- Do not modify operational settings or secrets without separate evidence.

### Bug-fixing criteria

Include this section only when the target involves code or behavior changes.

- First identify the likely root cause.
- Add or update a regression test when practical.
- Avoid symptom-only patches.
- Explain how the fix addresses the root cause.

### Boundary between Codex settings and AGENTS.md

`AGENTS.md` injects work context, prohibitions, verification criteria, and procedures. Runtime settings such as model, reasoning effort, sandbox, and approval policy generally belong in `config.toml`.

- Suggest or inspect setting files only when the user asks about Codex quality, model, or reasoning settings.
- If the user asked only to create a target `AGENTS.md`, do not create or modify `.codex/config.toml` or `~/.codex/config.toml` arbitrarily.
- Do not include config examples in the target `AGENTS.md` body by default; if needed, separate them as a suggestion in the final response.
- When proposing settings, first inspect the target's existing settings and the user's request.

### CLAUDE.md link

When the target needs a `CLAUDE.md`, create it as a symbolic link to `AGENTS.md` when possible.

```sh
ln -s AGENTS.md CLAUDE.md
```

If `CLAUDE.md` already exists, inspect its type first.

- If it is already a symlink to `AGENTS.md`, keep it.
- If it is a regular file or a link to a different target, do not overwrite it arbitrarily; ask the user.

On Windows, symlink creation may fail under normal user permissions. Use only a method that is possible in the target environment.

1. If Developer Mode is enabled or admin permission is available, PowerShell can create the symlink.

   ```powershell
   New-Item -ItemType SymbolicLink -Path CLAUDE.md -Target AGENTS.md
   ```

2. If Git for Windows is used, check `git config core.symlinks`.
3. If symlinks cannot be used, `CLAUDE.md` may be a regular file copy. In that case, state in the target `AGENTS.md` or contributing document that both files must be updated together.

After authoring, check the following where possible.

```sh
test -f AGENTS.md
git diff --check
git status --short
```

If `CLAUDE.md` was created, also check its link or file-sync state according to the environment.

### Separate document references

If the target has detailed documents split into separate files, do not duplicate all details in `AGENTS.md`. Instead, state which documents agents must read and in what order.

Check for the following document types.

- Operations documents: deployment, release, admin work, cache clearing, post-application verification
- Runtime or UI contract documents: DOM selectors, API contracts, schemas, routes, events, data attributes that code depends on
- Snippet or plugin documents: per-file registration locations, execution order, hook priority, required settings, verification commands
- Incident handling records: alert channels, triage principles, past decisions, status labels, actions that require user approval
- Document source management: generated files and source files, manually synchronized files, README generation rules
- Performance diagnosis documents: reproducible measurement methods, artifact locations, flags or environment notes needed for interpretation
- Security documents: secret injection locations, boundaries between public and private values, operational access cautions

If separate documents are found, summarize them in the target `AGENTS.md` using the following format. Do not keep example paths if the actual files do not exist.

```md
## Key reference documents

- `docs/operations.md`: Check deployment and operational application procedures.
- `docs/contracts.md`: Check external markup/API/schema contracts that code depends on.
```

Do not copy tables or long operational histories that already exist in detailed documents into `AGENTS.md`. Instead, specify which document to read first for each kind of task and when the document must be updated.

### Repeated mistake handling

If the same mistake repeats, do not immediately add a rule. First separate retrospective and proposal.

- Summarize the bad judgment in one sentence.
- Propose a concrete rule that would prevent the same mistake.
- Do not automatically update the target `AGENTS.md` or this repository's `AGENTS.md` without user approval.
- Prefer a rule that can be applied from the next task over an abstract principle.

### Load verification

Only when the user asks to confirm that `AGENTS.md` is actually being read, run or explain verification commands in the target environment. Use only commands that fit the available tools and approval policy, and do not report unrun results as successful.
