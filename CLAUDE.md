# CLAUDE.md — openmodularturretsteam.github.io

GitHub Pages site (Jekyll, theme `minima`) for the OpenModularTurretsTeam mods.
It holds the news posts (`_posts/`), the roadmap (`roadmap.md`), the about page (`about.md`), the CurseForge description draft (`curseforge-description-omt.md`) and the merged changelogs (`changelog-<version>.md`).

## Sources

The site does not invent changes: everything it says about a release comes from the mods' own changelogs.
They are in the two workspaces next to this repo:

| Version line | Folder | Changelogs |
| --- | --- | --- |
| 1.12.2 (Forge) | `../OMTTeam1.12` | `OpenModularTurrets/CHANGELOG.md`, `OMLib/CHANGELOG.md`, `OpenModularPassiveDefense/CHANGELOG.md` |
| 1.20.1+ (Fabric 1.20.1/1.21.1, NeoForge 1.21.1, Forge 1.20.1) | `../OMT1.20.1+` | `CHANGELOG.md` (OMPD and OMLib are part of OMT there) |

`../OMTTeam1.12/OpenModularLighting/CHANGELOG.md` is the changelog of Open Modular Lighting (own versions, 1.0.x); it is not part of the OMT changelog.
Each changelog follows Keep a Changelog (`## [version] - date`, sections Added, Changed, Fixed, Removed, and `## [Unreleased]`).
Read the version and date of the latest release from these headings, not from git tags.

## Merged changelog (`changelog-4.0.0.md`, permalink `/changelog/4.0.0/`)

One page per major version merges all its alpha and beta releases of both version lines, so it can be linked as the full changelog.
When a mod releases, update it like this:

1. Read the new release sections in all four changelogs (and their *Unreleased* sections).
2. Merge each entry into the right section of the page; do not list releases one by one.
   Sections, in order: Before you update, Added, Changed, Removed, Fixed, For mod and addon developers, Coming in the next pre-release, Release history.
   Added and Changed have topic subsections (Versions and loaders, Turrets, Targeting and aiming, Turret bases …); keep using them.
3. Prefix:
   - An entry that describes the same change on both version lines gets **one** line without prefix.
     Check the source code of both workspaces when the wording differs but the change may be the same (the core logic is shared, e.g. `core/turret/RayMath.java`).
   - Otherwise the line starts with `**1.12.2 only:**` or `**1.20.1+ only:**`.
   - 1.12.2 entries from OMLib or OMPD start with `**1.12.2 only** · _OMLib_:` or `**1.12.2 only** · _OMPD_:`.
   - Order inside a section: shared lines first, then `1.12.2 only`, then `1.20.1+ only`.
4. Merge, don't append: when a later release changes or undoes an earlier entry, write the final state once (e.g. "Relativistic Turret renamed internally" + "renamed in all languages" → one line).
   Drop entries that a later release made obsolete (e.g. "Not yet implemented: camo" once camo was added).
   Fixes of bugs that only existed in earlier pre-releases stay, with their prefix.
5. *Unreleased* entries go under "Coming in the next pre-release"; on release, move them into the main sections.
6. Update the version table at the top and the Release history table (version, date per version line).
7. Wording: one line per entry, written for players, close to the source entry; no trailing periods; mod developer API entries go under "For mod and addon developers".

## Other pages

- A new release that players should hear about gets a post in `_posts/YYYY-MM-DD-<slug>.markdown` (front matter `layout: post`, `categories: update`) with the highlights and a link to the merged changelog.
  Keep the post date in the past (Jekyll does not publish future posts).
- `roadmap.md` and `curseforge-description-omt.md` list the state per version (`(**done**)`, `(**WIP**)`); update them to match the changelogs.

## Build

Jekyll 4.4 with Bundler (Arch: `pacman -S ruby-bundler`); the gems go into `vendor/bundle` (`bundle config set --local path vendor/bundle`, git-ignored and excluded in `_config.yml`).

```bash
bundle install
bundle exec jekyll build   # into _site/
bundle exec jekyll serve   # http://localhost:4000
```

The Sass deprecation warnings come from the minima theme and can be ignored.
GitHub Pages builds the published site itself and does not use the Gemfile.
