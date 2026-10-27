# CLAUDE.md — openmodularturretsteam.github.io

GitHub Pages site (Jekyll, theme `minima`) for the OpenModularTurretsTeam mods.
It holds the news posts (`_posts/`), the roadmap (`roadmap.md`), the about page (`about.md`), the CurseForge description draft (`curseforge-description-omt.md`) and the merged changelogs (`changelog-4.0.0.md` for OMT, `changelog-oml-1.0.0.md` for OML).

## Sources

The site does not invent changes: everything it says about a release comes from the mods' own changelogs.
They are in the two workspaces next to this repo:

| Version line | Folder | Changelogs |
| --- | --- | --- |
| 1.12.2 (Forge) | `../OMTTeam1.12` | `OpenModularTurrets/CHANGELOG.md`, `OMLib/CHANGELOG.md`, `OpenModularPassiveDefense/CHANGELOG.md` |
| 1.20.1, 1.21.1 and 1.21.11 (Fabric 1.20.1/1.21.1/1.21.11, NeoForge 1.21.1/1.21.11, Forge 1.20.1) | `../OMTTeam1.20.1+` (workspace folder and branches keep the name "1.20.1+") | `OpenModularTurrets/CHANGELOG.md` (OMPD's content is part of OMT there), `OMLib/CHANGELOG.md` (the library that OMT and OML bundle; its entries go under OMLib/OMT, see below) |

Open Modular Lighting (OML) has its own versions (1.0.x) and its own merged changelog page; it is not part of the OMT changelog.
Its two branches share one changelog history (the version numbers are shared: beta.1 to beta.5 were only released for the modern versions, beta.6 is the first 1.12.2 build), and each branch adds its own releases:

| Version line | Folder | Changelog |
| --- | --- | --- |
| 1.12.2 (Forge, needs OMLib) | `../OMTTeam1.12/OpenModularLighting` (branch `1.12`) | `CHANGELOG.md` (entries start with "Forge 1.12.2:") |
| 1.20.1, 1.21.1 and 1.21.11 | `../OMTTeam1.20.1+/OpenModularLighting` (branch `1.20.1+`) | `CHANGELOG.md` |

On the modern versions OMLib is a library that both mods bundle (since OMT 4.0.0-beta.10 and OML 1.0.0-beta.9); it has no page of its own.
Its changelog is empty so far; when it gets entries, describe the user-visible ones on the OMT and OML pages and the developer-facing ones under "For mod and addon developers" with the `_OMLib_` marker, as for 1.12.2.

Each changelog follows Keep a Changelog (`## [version] - date`, sections Added, Changed, Fixed, Removed, and `## [Unreleased]`).
Read the version and date of the latest release from these headings, not from git tags.

## Merged changelogs

`changelog-4.0.0.md` (OMT, permalink `/changelog/4.0.0/`) and `changelog-oml-1.0.0.md` (OML, permalink `/changelog/oml-1.0.0/`) follow the same rules.
One page per major version merges all its alpha and beta releases of both version lines, so it can be linked as the full changelog.
When a mod releases, update it like this:

1. Read the new release sections in all changelogs of the mod (and their *Unreleased* sections).
2. Merge each entry into the right section of the page; do not list releases one by one.
   Sections, in order: Before you update, Added, Changed, Removed, Fixed, For mod and addon developers, Coming in the next pre-release, Release history.
   Added and Changed have topic subsections (Versions and loaders, Turrets, Targeting and aiming, Turret bases …); keep using them.
3. Prefix:
   - An entry that describes the same change on both version lines gets **one** line without prefix.
     Check the source code of both workspaces when the wording differs but the change may be the same (the core logic is shared, e.g. `core/turret/RayMath.java`).
   - OML: the 1.12.2 branch is a port with the same `core/` and `config/` code, so a feature of the shared history counts for both lines when the 1.12.2 source has it; only loader-specific lines (Jade/Hwyla, energy API, OMLib, disguise menu) get a prefix.
   - Otherwise the line starts with `**1.12.2 only:**` or, for the modern versions, `**1.20.1/1.21.1/1.21.11 only:**` (OMT and OML pages).
     Do not write "1.20.1+" on the site: name the supported Minecraft versions.
   - 1.12.2 entries from OMLib or OMPD start with `**1.12.2 only** · _OMLib_:` or `**1.12.2 only** · _OMPD_:`.
   - Order inside a section: shared lines first, then `1.12.2 only`, then the modern versions' prefix.
4. Merge, don't append: when a later release changes or undoes an earlier entry, write the final state once (e.g. "Relativistic Turret renamed internally" + "renamed in all languages" → one line).
   Drop entries that a later release made obsolete (e.g. "Not yet implemented: camo" once camo was added).
   Fixes of bugs that only existed in earlier pre-releases stay, with their prefix.
5. *Unreleased* entries go under "Coming in the next pre-release"; on release, move them into the main sections.
   Leave the section out while no changelog has unreleased entries.
   A change released on one version line but still unreleased on the other is listed in the main sections with the released line's prefix and under "Coming" with the other's; once both are released, it becomes one line without prefix.
6. Update the version table at the top and the Release history table (version, date per version line).
7. Wording: one line per entry, written for players, close to the source entry; no trailing periods; mod developer API entries go under "For mod and addon developers".

## Markdown style

Write strong emphasis (bold) with stars (`**bold**`), never with underscores (`__bold__`); italics use single underscores (`_italic_`).

## Other pages

- Write a new post only for a regular (non-pre-release) version, or when the user asks for one.
  Alpha and beta releases get no post: update the changelog pages, the roadmap and the CurseForge description instead.
- A post goes in `_posts/YYYY-MM-DD-<slug>.markdown` (front matter `layout: post`, `categories: update`) with the highlights and a link to the merged changelog.
  Keep the post date in the past (Jekyll does not publish future posts).
- The header menu shows only what `header_menu` in `_config.yml` lists: page paths, and dropdowns with a `title` and `pages` (rendered by `_includes/header.html`, an override of minima's header; styles in `assets/main.scss`).
  Add a new page there; a new changelog page goes into the "Changelogs" dropdown.
- Dark theme: optional, follows the system setting unless the visitor picks Light or Dark with the "Theme" button in the header (saved in `localStorage`, applied early by `_includes/head.html`).
  The colours are in `assets/main.scss` (`dark-theme` mixin); a new element with its own colours needs a dark variant there.
- `roadmap.md` and `curseforge-description-omt.md` list the state per version; update them to match the changelogs.
  The planned versions of OMT (4.1.x, 4.2.x) come from the confirmed issues (label `confirmed`, milestones) of https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues; link each item to its issue and leave out unconfirmed ones.
  They mark the state as `(**done**)` or `(**WIP**)`.

## Build

Jekyll 4.4 with Bundler (Arch: `pacman -S ruby-bundler`); the gems go into `vendor/bundle` (`bundle config set --local path vendor/bundle`, git-ignored and excluded in `_config.yml`).

```bash
bundle install
bundle exec jekyll build   # into _site/
bundle exec jekyll serve   # http://localhost:4000
```

The Sass deprecation warnings come from the minima theme and can be ignored.
GitHub Pages builds the published site itself and does not use the Gemfile.
