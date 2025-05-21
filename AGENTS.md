# Repository Guidelines

This repository is a backup of an **Obsidian** vault. The majority of the content consists of Markdown notes organised into directories with emoji prefixes. Image files live in an `_assets` folder, either at the repository root or within a note directory.

## Editing Notes
- Use **Markdown (`.md`)** for all notes.
- Some notes start with a YAML front‑matter block delimited by `---`. Preserve it when present and keep the fields intact.
- Internal links use Obsidian wiki syntax: `[[Page Name]]` or `[[Page Name#Heading|Alias]]`.
- Do not remove the `%% Begin Waypoint %%` / `%% End Waypoint %%` markers. They are used to regenerate automatic index sections.
- Keep filenames, including emoji and spaces, exactly as they are. When using shell commands you may need to quote the paths.
- Place images inside the `_assets` folder that corresponds to the note (global `_assets` at the repository root or a local `_assets` subfolder). Reference them with `![[image-name.ext]]`.

## Commit Messages
- Write short descriptive commit messages, e.g. `Add note about X` or `Update Y.md`.
- The repository currently does not include automated tests. Before committing, run `git status` to ensure only intended files are added.

## Pull Requests
- Summarise notable changes in the PR description.
- If programmatic checks are added in the future, run them before submitting.
