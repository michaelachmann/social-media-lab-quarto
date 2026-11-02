# Agent instructions

## Project and current focus

This repository contains the source for social-media-lab.net, a public Quarto
website for teaching and research on computational social media analysis and
political communication. The executable code supplement lives in the separate
`michaelachmann/social-media-lab` repository.

The current revision targets the winter semester 2026/27: improve and streamline
existing pages and add selected new content. Work on the requested scope;
`TODO.md` contains possible work, not authorization to implement every item.

## Language and editorial approach

- Write website content in English. Communicate with the user in German.
- Keep explanations accessible to students and connect methods to their research
  purpose, assumptions, and evaluation.
- Preserve useful existing material and the site's conventions. Prefer focused
  improvements over wholesale rewrites unless the task calls for one.
- Verify changing claims about tools, models, APIs, data access, and availability
  against current primary sources. Distinguish evidence from suggestions and
  limitations; do not invent references, findings, or course details.
- Reuse citation keys from `literature.bib`; add verified references there when
  needed. Pages normally use a relative bibliography path and `@citekey` syntax.
- Update dates and semester references when substantively revising content;
  preserve original publication dates where appropriate and use `date-modified`
  for revisions. Do not change dates merely to imply freshness.

## Maintainability

- Keep changes small, coherent, and easy to maintain. Reuse existing structure,
  styles, and Quarto features before adding dependencies or custom machinery.
- Avoid duplicated content, unnecessary generated files, and unrelated cleanup.
- Preserve existing URLs and relative links where practical. When moving or
  renaming content, update navigation, links, embeds, and related metadata.
- Treat historical material deliberately: make its status clear when relevant;
  do not silently delete or modernize examples beyond the requested scope.

## Structure and Quarto conventions

- `_quarto.yml` defines the site, sidebar, navbar, HTML theme, and resources.
  Add new teaching pages to the appropriate navigation or link them explicitly
  from an existing page so students can find them.
- Main sections are `getting-started/`, `basics/`, `data-collection/`,
  `processing/` (Text Analysis), `image-analysis/`, `evaluation/`, `reporting/`,
  and `projects/`.
- `notebooks/` holds notebooks with saved outputs. Pages embed cells with Quarto
  embed shortcodes and may provide `notebook-view` metadata. Keep file paths,
  notebook titles, and supplement links consistent.
- Preserve saved notebook outputs during normal content work. Do not execute
  notebooks or invoke paid APIs just to preview or render prose changes.
  `_quarto.yml` sets `execute.freeze: auto`; when checking content, explicitly
  disable execution rather than relying on freeze alone.
- Follow neighboring pages for frontmatter, including title, author details,
  license, bibliography, and citation metadata. Do not invent or change a DOI.
- `styles.css` holds shared styling. The blog scaffold (`blog.qmd`, `posts/`)
  is currently disabled in the navbar.
- Preserve `CNAME`, `.nojekyll`, and the `CNAME` resource entry needed for hosting.

## Public repository and artifacts

Everything committed here is public. Do not commit credentials, private course
or student information, unpublished private material, personal working notes,
or other artifacts intended to remain private. Check notebook outputs,
screenshots, metadata, and data files as well as prose before staging changes.

Keep temporary drafts and verification artifacts outside the repository when
they are not intended for publication. Do not commit `_site/`, `.quarto/`,
caches, or incidental render artifacts. Stage only files belonging to the task;
leave unrelated changes intact.

## Workflow and verification

- Create a dedicated `codex/<descriptive-name>` branch for each task before
  editing. Continue on that branch for follow-ups belonging to the same task.
- Edit and verify autonomously within the requested scope. Commit, push, open
  pull requests, and publish only when the user requests those actions.
- There is no configured automated test or lint suite. For content changes,
  render the affected pages with execution disabled, then inspect layout,
  navigation, citations, images, links, and notebook embeds as relevant.
- For site-wide configuration or navigation changes, render the full site with
  execution disabled. Report material warnings and any checks that could not
  be completed. Do not add test infrastructure for routine prose edits.
- An instructions-only change does not require a website render.

### Shell commands

Always prefix shell commands with `rtk`, including each segment in a command
chain. Use `rtk proxy <command>` when unfiltered output is needed for debugging.

```bash
rtk git status --short
rtk git switch -c codex/describe-task
rtk quarto render path/to/page.qmd --no-execute
rtk quarto render --no-execute
rtk quarto preview --no-execute
```

Publishing uses `rtk quarto publish gh-pages` and requires an explicit user
request to publish.
