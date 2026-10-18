# para.kb

**PARA**, a KB type for [AutoDoc](https://github.com/yongjohnlee80/autodoc).

PARA, after Tiago Forte: everything is filed by how actionable it is, not by topic. Projects have a goal and a deadline. Areas are responsibilities you keep up over time. Resources are topics of interest. Archives hold what's inactive. A note moves between them as its life changes.

## Folders

| Folder | Purpose |
|---|---|
| `projects/` | goals with a deadline, one folder per project |
| `areas/` | responsibilities kept up over time, with no end date |
| `resources/` | topics of interest and reference material |
| `archives/` | inactive projects, areas and resources |
| `_templates/` | a template per note type |
| `_schema/` | the frontmatter types this KB validates |

Every folder gets an `ABOUT.md` (`_ABOUT.md` in the `_` folders) saying what belongs there. The root
gets `AGENTS.md` (the agent contract), `ABOUT.md`, `RULES.md` (your own rules), and `CLAUDE.md` and
`GEMINI.md`, which point agents at `AGENTS.md`. AutoDoc adds `KB_OPERATIONS.md`, its own manual for
searching and writing through AutoDoc.

## How it works

- **Projects:** a goal with a deadline ("launch the site by June"). One folder per project.
- **Areas:** a standard to keep up, with no end date ("health", "finances", "the team").
- **Resources:** a topic you're interested in or gathering material on.
- **Archives:** anything inactive from the other three: a finished project, an area you've let go.
- **Move, don't copy.** When a project ends, its folder moves to `archives/`. File by "where will I use this next?".

## Use it

In AutoDoc: **Workspace › Add…**, pick a root (or **New Folder**), and choose **PARA** as the KB type.
For a workspace you already have: **Apply KB type…** in the workspace manager.

AutoDoc only ever creates files. It never overwrites or deletes one you have, so applying a type to
an existing folder adds what is missing and changes nothing else.

## This repository

Every AutoDoc KB type has the same layout:

```text
kbtype.toml    what the type is, its folders and their purposes, the workspace settings it proposes
tree/          the KB as it is created: every file here is copied into the new KB, create-only
README.md      this file (never copied)
```

Nothing here runs: AutoDoc reads `kbtype.toml` and copies `tree/`'s text files. To make your own
type, fork this repo, change `kbtype.toml` and `tree/` together (every `[[folder]]` needs its
`ABOUT.md` in `tree/`, and every folder in `tree/` needs its `[[folder]]`), and give AutoDoc your
repo's URL.

## License

Apache License 2.0. See [LICENSE](LICENSE).
