---
name: dont-repeat-yourself
description: "Use when saving a user-approved coding solution for future reuse, or starting a task that resembles a saved script, workflow, or diagnostic recipe. Also matches 记住这个、下次复用、这个脚本很好、经验复用. Skip unrelated tiny edits and do not save a guessed reconstruction as a tested artifact."
license: MIT
metadata:
  author: "kevin-12-ou"
  version: "1.0.0"
  repository: "https://github.com/kevin-12-ou/dont-repeat-yourself"
---
# Don't Repeat Yourself

Turn a successful coding outcome into a small, searchable recipe that a future agent can apply without rereading the chat. The personal library is in the directory containing this SKILL.md: library/INDEX.md, library/recipes/, and library/artifacts/. Keep the index short; read full recipes only when relevant.

## Reuse in a new task

1. For a new coding project or a task that plausibly repeats earlier work, scan library/INDEX.md by goal, technology, and failure symptom. If no entry matches, proceed normally; do not scan old chats or load the whole library.
2. Open only the most relevant one to three recipes. Compare their "Use when", "Avoid when", prerequisites, source version, and verification against the current repository and user goal. Inspect current code and dependencies before reusing anything.
3. Reuse the smallest applicable artifact or workflow. Adapt project-specific paths, versions, credentials, and assumptions. Run the checks that matter in the new environment. Tell the user what was reused, what changed, and what remains unverified.
4. If a recipe is stale, update its limits or verification after checking the current evidence. Do not silently treat an old success as current proof.

## Capture after success

Capture when the user asks to save or reuse the result. Also capture after the user confirms a working solution when it contains a repeatable script, sequence, diagnostic insight, or pitfall that would otherwise require meaningful rediscovery. A routine one-off edit needs no entry unless the user explicitly asks to save it.

1. Read the actual final files and relevant test or user feedback. If the solution is only referenced in an inaccessible chat or file, ask for the source; do not reconstruct it from memory. Record the evidence level accurately: locally verified, user confirmed, or unverified.
2. Search INDEX.md and existing recipes for the same problem. Update the canonical recipe when the new result improves it; do not create a near duplicate.
3. Create or update one focused recipe using references/recipe-template.md. Include the goal, applicability limits, prerequisites, steps or command, adaptation points, failed approaches worth avoiding, exact source location or revision, and verification. Use the user's language where helpful.
4. For a small self-contained script, copy the final working file into library/artifacts/<slug>/ and link it from the recipe. For larger code, preserve only the reusable component and link to the source repository, revision, and paths. Never present a paraphrased reconstruction as the tested artifact.
5. Remove secrets, personal data, and machine-specific values from any copied artifact, then state the replacements in the recipe. Respect source licenses; if copying third-party code is not clearly permitted, link to the upstream source instead.
6. Add one concise INDEX.md row with a searchable "Use when" phrase, keywords, evidence, and update date. Check that every link and copied file resolves. Report the saved paths to the user.

Do not automatically rewrite global instructions, publish the library, install dependencies, or apply a recipe to another project as part of capture. The index and recipe are the handoff; the next task still needs current-context checks.
