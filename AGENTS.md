# agents-md root instructions

This root `AGENTS.md` is the active instruction file for maintaining the `agents-md` repository itself. It also routes tasks that create or update `AGENTS.md` files for other repositories or document sets to the localized reference instructions under `agents/`.

## Scope

Use this file for work on the `agents-md` repository itself.

Use localized reference files only when creating or updating an `AGENTS.md` file for another target.

- English external-reference instructions: `agents/AGENTS.en.md`
- Korean external-reference instructions: `agents/AGENTS.kr.md`

Localized files are for external target generation and update work. They are not the maintenance instructions for this repository.

## Reference-use rule

If the user or another instruction says to reference this document, that means to follow the rules in these instructions. It does not mean to copy this document's structure, section order, examples, file layout, or repository-specific maintenance rules into a target `AGENTS.md`.

When creating or updating a target `AGENTS.md`, inspect the target first and write instructions that fit the target's confirmed context.

## Language routing

- Write this root `AGENTS.md` in English.
- Keep the default external-reference language as English.
- Use `agents/AGENTS.en.md` when the target language is English or cannot be confirmed.
- Use `agents/AGENTS.kr.md` when the user's preferred language, work environment, or primary communication context is Korean.
- Infer language only from confirmed evidence: user messages, existing README/docs/contributing files, existing `AGENTS.md` or `CLAUDE.md`, and the tone of commits, issues, or pull requests.
- By default, infer the user's preferred language and respond in that language.
- If the user explicitly specifies a response language or target document language, follow that instruction.
- If an existing target `AGENTS.md` uses a different language from the inferred target language, preserve the existing document language and make only the minimal required changes unless the user explicitly asks for a full translation or language switch.

When introducing language routing to a target that does not already have it:

- Keep the target root `AGENTS.md` in English.
- Use the target root `AGENTS.md` as a router and agent role description.
- Put detailed target instructions under `agents/AGENTS.<language>.md`, such as `agents/AGENTS.en.md` or `agents/AGENTS.kr.md`.
- Do not force this file layout onto an existing target if the user only asked for a conservative update.

## Instruction priority

For this repository, apply instructions in this order.

1. Latest explicit user instruction
2. This root `AGENTS.md`
3. Relevant localized file under `agents/`, only for external target generation or update work
4. Existing conventions in the files being edited

For external target work, inspect the target's own instruction files and documentation before editing. Do not override target-specific instructions with generic `agents-md` text unless the user explicitly asks for that change.

## Common working principles

- Put the conclusion first and separate unverified information clearly.
- Do not use unnecessary praise, exclamations, or decorative phrasing.
- Before answering or editing, read the relevant files and existing documentation.
- Do not guess repository structure, APIs, environment variables, commands, document generation methods, or deployment procedures.
- For non-trivial work, first make a short plan with likely files to change, expected behavior, and verification method.
- If a request is ambiguous, choose the safest minimal interpretation and state that interpretation.
- Make changes as small and localized as possible.
- Preserve existing behavior, public APIs, and documentation source-of-truth relationships.
- Do not perform broad structural changes or large refactors unless the user explicitly asks for them.
- Do not change formatting that is unrelated to the request.
- Treat already modified files as user or prior-work changes and do not revert them arbitrarily.
- Do not write secrets, tokens, or credentials into the repository.
- Do not modify production config, deployment settings, analytics keys, or operational access information without an explicit user request and confirmed context.
- Do not claim commands, tests, deployments, or file states succeeded unless they were actually run or inspected.
- Do not ignore failed verification. Separate the failure cause from whether it is related to the changes.

Do not insert content into commit messages, code comments, PR/issue bodies, documents, or config files unless the user explicitly requested it. In particular, do not add:

- trailers such as `Co-Authored-By` or `Signed-off-by`
- agent, model, provider names, or provider email addresses
- generation-tool labels such as "Generated with ..." or "Made by AI"
- unrelated advertising, promotion, or external links

Even if there seems to be a good reason to add such content, ask the user first and add it only after approval.

## Repository role

`agents-md` manages instructions for creating and updating `AGENTS.md` files for personal projects.

- The root `AGENTS.md` is the source of truth for maintaining this repository and for routing to localized external-reference files.
- `agents/AGENTS.en.md` is the English external-reference instruction file.
- `agents/AGENTS.kr.md` is the Korean external-reference instruction file.
- Localized files must contain only instructions for creating or updating target repositories' `AGENTS.md` files.
- Keep `CLAUDE.md` as a symbolic link to the root `AGENTS.md`; do not duplicate it as a separate file.
- When adding or changing a rule, decide whether it belongs in this root file, the localized external-reference files, or both.

## Start-of-work checklist

At the start of work on this repository, check the following first.

- `git status --short`
- existing tone and structure of the files to change
- whether `CLAUDE.md` is a symbolic link to the root `AGENTS.md`
- whether localized external-reference files must be updated together
- whether any separate document must be referenced

## Source management

- The source of truth for this repository's active instructions is the root `AGENTS.md`.
- The source of truth for English external-reference instructions is `agents/AGENTS.en.md`.
- The source of truth for Korean external-reference instructions is `agents/AGENTS.kr.md`.
- If a language-independent external-reference rule changes, reflect the same meaning in every localized external-reference file or state which files were not updated in the final response.
- If an internal maintenance rule changes, keep it in this root file and do not duplicate it into localized external-reference files unless it also affects target generation behavior.
- The source of truth for README is `resources/README.preset.md`.
- Do not finish by editing `README.md` directly; edit `resources/README.preset.md` and run `./scripts/readme_update.sh`.
- The source of truth for the README hero SVG is `resources/readme-hero.preset.svg`.
- `resources/readme-hero.svg` is generated, so do not finish by editing it directly; regenerate it with `./scripts/readme_update.sh`.
- `agents/AGENTS.<language>.md` files are localized reference instructions, not presets to copy verbatim into target `AGENTS.md` files.
- Do not create a separate preset file for generating target `AGENTS.md` files.
- Write for general personal projects and do not include specific company names, clients, private product names, operational channels, or internal URLs.

## Documentation standards

- Write the root `AGENTS.md` in English.
- Write `agents/AGENTS.en.md` in English.
- Write `agents/AGENTS.kr.md` in Korean.
- Keep section titles short and clear.
- Do not mix repository-specific maintenance rules into localized external-reference files.
- Do not phrase target-generation rules in a way that requires copying this repository's structure into every target.
- Do not finish by editing generated files directly; edit the source file and run the generation command when a source/generation relationship exists.
- If document sources and embedded text in code must be synchronized manually, update both.
- When adding a new rule, make clear which failure case it is meant to prevent.

## Updating existing target AGENTS.md files from this repository

When the user asks to update an already-created target `AGENTS.md` based on this repository or this page, treat that as external-reference update work.

- Use the appropriate localized reference file under `agents/`.
- Read the target's existing `AGENTS.md`, nested instruction files, `CLAUDE.md`, README, docs, and contributing documents first.
- Preserve target-specific roles, commands, paths, verification procedures, and prohibitions that are confirmed in the existing target.
- Do not rewrite the target from scratch unless the user explicitly asks for a full rewrite.
- Do not impose this repository's root/localized file structure on the target unless the user asks to introduce language routing or the target already uses that structure.
- If existing target instructions conflict with this repository's guidance, report the conflict and ask before removing target-specific rules.

## Commit principles

Commit only when the user asks for it.

Use the following prefixes and English Sentence Case in commit messages.

- Feature addition: `Feat: ...`
- Documentation update: `Docs: ...`
- Naming or structure cleanup: `Refactor: ...`
- Bug fix: `Fix: ...`
- Configuration change: `Chore: ...`
- Test addition or update: `Test: ...`

Unless the user explicitly requests a different rule, these rules take priority over recent commit style.

Keep one purpose per commit. For example, separate the following.

- feature code changes
- generated documentation updates
- config file changes
- dependency lockfile updates
- operational response record updates

Even if the user asks for a commit, do not stage unrelated changes. If user changes and task changes are mixed in the same file, inspect the diff and stage only the required hunks.

## Verification criteria

After changes, run the following within the possible scope.

- README change: `./scripts/readme_update.sh`
- README hero change: `./scripts/readme_update.sh`
- `git diff --check`
- `git status --short`
- If symlink verification is needed: `ls -l CLAUDE.md`
- If root/localized instruction separation changed: `test -f AGENTS.md`, `test -f agents/AGENTS.en.md`, `test -f agents/AGENTS.kr.md`

Do not report unverifiable items as successful. Report why they could not be verified.

## Final response format

After finishing work, always include the following.

1. Summary of changes
2. Files changed
3. Verification commands run and results
4. Remaining risks, limitations, or follow-up

If no code changed or only documentation changed, state that explicitly.
