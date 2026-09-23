# Prisant Labs

**Tailored tools for people who tinker or live in their editors, agents, and file systems.**

Prisant Labs is where [@jprisant](https://github.com/jprisant) tinkers, experiments, and publishes tools built first for personal daily use, then hardened for everyone else. Most of it is local-first, runs natively on Windows, and is built to leave your files alone unless you tell it otherwise.

Version badges on this page update themselves. Status lines are written by hand and say plainly how far along each project is.

## At a glance

**[Agent tooling](#agent-tooling)**

- [prisant-utilities](#prisant-utilities) - eight agent skills for session continuity, decision briefs, peer review, specs, and release planning · *active*
- [agent-workspace-tools](#agent-workspace-tools) - `awt`, an offline CLI that moves a project and its Claude Code history together · *pre-release*
- [agent-plugins](#agent-plugins) - the plugin marketplace to install from · *live*

**[Knowledge and writing tools](#knowledge-and-writing-tools)**

- [obsidian-tag-visibility](#obsidian-tag-visibility) - hide and flag noisy tags across a vault without editing notes · *stable*
- [obsidian-vault-collection](#obsidian-vault-collection) - answer-keyed test vaults and starter vaults for PKM methods and roles · *stable*
- [typora-plugin-outline-view](#typora-plugin-outline-view) - a synchronized outline in Typora's right dock · *released*

**[Desktop utilities](#desktop-utilities)**

- [repo-sync-tool](#repo-sync-tool) - a tray app that keeps cloned repos fresh without touching your work · *public beta*
- [audiobook-organizer](#audiobook-organizer) - scan an audiobook library and rehearse a tidy-up before anything moves · *alpha*

**[3d print models](#3d-print-models)**

- [3d-cable-box-parametric-openscad](#3d-cable-box-parametric-openscad) - a parametric cable box with bed slicing and snap-fit seams · *stable, v2 in RC*

---

## Agent tooling

For people who work with Claude Code or Codex every day.

### [prisant-utilities](https://github.com/prisant-labs/prisant-utilities)

![release](https://img.shields.io/github/v/release/prisant-labs/prisant-utilities?style=flat-square) ![marketplace pin](https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/prisant-labs/agent-plugins/main/.claude-plugin/marketplace.json&query=%24..version&label=marketplace&prefix=v&color=blue&style=flat-square) ![status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/prisant-utilities?style=flat-square)

Agent skills for the work around the work: closing a session so tomorrow can pick it up, turning raw thinking into a decision, and carrying a feature from spec to a taggable release.

**What's inside:** eight skills, all prefixed `plab-`, for Claude Code and Codex.

- `plab-wrap-session` and `plab-continue-session`: a matched pair that writes a structured session log, then resumes from it
- `plab-strategy-brief`: turns a brain dump into a decision-ready analysis
- `plab-guide`: builds a guide bundle (Markdown, an ADHD-formatted variant, a quick-reference HTML page, and a short PDF)
- `plab-ai-review`: runs a structured peer review of a document with a second model
- `plab-spec` and `plab-release-plan`: numbered, source-cited acceptance criteria, then a release plan that gates the tag
- `plab-init-project`: scaffolds agent infrastructure into a repo (manual invocation only)

**Status:** actively released, with frequent point releases. Installs from the Prisant Labs marketplace, which sometimes pins one release behind the latest.

### [agent-workspace-tools](https://github.com/prisant-labs/agent-workspace-tools)

![version on main](https://img.shields.io/badge/dynamic/toml?url=https://raw.githubusercontent.com/prisant-labs/agent-workspace-tools/main/Cargo.toml&query=%24.workspace.package.version&label=main&prefix=v&color=orange&style=flat-square) ![status](https://img.shields.io/badge/status-pre--release-orange?style=flat-square) ![platform](https://img.shields.io/badge/platform-Windows-0078D6?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/agent-workspace-tools?style=flat-square)

`awt` moves a project folder and brings its Claude Code history with it. Claude Code keys session state to a project's path, so a plain move orphans it. `awt` plans the move, applies it, verifies it, and can roll it back. Deterministic and offline: no LLM, no network.

**What's inside:** a Rust CLI with `doctor`, `scan`, `plan`, `apply`, `verify`, `rollback`, `list`, `archive`, `associate`, and `repair`.

**Status:** pre-release, in active development. v1.0 is feature-complete but not yet tagged, so for now you build it from source with `cargo install`. Windows only.

### [agent-plugins](https://github.com/prisant-labs/agent-plugins)

![plugins listed](https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/prisant-labs/agent-plugins/main/.claude-plugin/marketplace.json&query=%24.plugins.length&label=plugins%20listed&color=blue&style=flat-square) ![last commit](https://img.shields.io/github/last-commit/prisant-labs/agent-plugins?style=flat-square)

The Prisant Labs plugin marketplace. Add it once and every plugin published here becomes available, including future ones.

```
/plugin marketplace add prisant-labs/agent-plugins
/plugin install prisant-utilities@prisant-labs
```

**What's inside:** only the catalog. There's a single `marketplace.json`, and each plugin keeps its own repository, versions, and issues.

**Status:** live. prisant-utilities is available now. A second plugin is listed early so the marketplace name stays stable, and it will install once its repository goes public.

---

## Knowledge and writing tools

For Obsidian and Typora users.

### [obsidian-tag-visibility](https://github.com/prisant-labs/obsidian-tag-visibility)

![release](https://img.shields.io/github/v/release/prisant-labs/obsidian-tag-visibility?style=flat-square) ![status](https://img.shields.io/badge/status-stable-brightgreen?style=flat-square) ![platform](https://img.shields.io/badge/Obsidian-desktop%20%2B%20mobile-7C3AED?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/obsidian-tag-visibility?style=flat-square)

Hide, flag, and surface noisy tags across your whole vault without modifying a single note.

**What's inside:**

- A dockable Tag Visibility panel that can open beside the tag pane
- Four scopes you switch on separately: tag pane, Notebook Navigator, Properties, and autocomplete
- Per-tag always-show and always-hide overrides
- Five built-in presets, plus custom regex, frequency, and list rules
- A panic command that turns everything off at once

**Status:** v1.0 has shipped, with v1.1 and v1.2 planned. It isn't in Obsidian's plugin directory yet, so for now you install it with BRAT or manually. Works on desktop and on mobile.

### [obsidian-vault-collection](https://github.com/prisant-labs/obsidian-vault-collection)

![release](https://img.shields.io/github/v/release/prisant-labs/obsidian-vault-collection?style=flat-square) ![status](https://img.shields.io/badge/status-stable-brightgreen?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/obsidian-vault-collection?style=flat-square)

Ready-made Obsidian vaults: some for testing plugins, some for trying out a note-taking method before you commit to it.

**What's inside:** twelve vaults in three families.

- **Testing vaults:** four deterministic vaults of 20, 200, 2,000, and 20,000 notes. Each has an answer key, so a plugin's output can be checked against known truth.
- **Method vaults:** hand-authored starters for PARA, Zettelkasten, Maps of Content, and GTD.
- **Role vaults:** starters for a student, a writer, a researcher, and a software developer.

**Status:** stable since 1.0.0, and still adding vaults. Download a single vault as a zip from Releases. Needs Obsidian 1.9.10 or later.

### [typora-plugin-outline-view](https://github.com/prisant-labs/typora-plugin-outline-view)

![release](https://img.shields.io/github/v/release/prisant-labs/typora-plugin-outline-view?style=flat-square) ![version on main](https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/prisant-labs/typora-plugin-outline-view/main/src/manifest.json&query=%24.version&label=main&prefix=v&color=orange&style=flat-square) ![platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS-555?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/typora-plugin-outline-view?style=flat-square)

Outline View puts a synchronized heading outline in Typora's right dock, so the Files panel can stay open on the left.

**What's inside:**

- A live H1 to H6 outline with click navigation, which follows the heading you're on
- Heading-range selection by drag, click, or keyboard
- A choice of selector styles, plus styling for each heading level
- Commands to toggle, refresh, expand all, and collapse all

**Status:** 0.3.0 is released and listed in Typora's Community Plugin marketplace. A 0.3.1 candidate is in progress on `main`. Supports Windows and macOS.

---

## Desktop utilities

Local-first Windows desktop apps built with Rust and Tauri.

### [repo-sync-tool](https://github.com/prisant-labs/repo-sync-tool)

![release](https://img.shields.io/github/v/release/prisant-labs/repo-sync-tool?include_prereleases&style=flat-square) ![status](https://img.shields.io/badge/status-public%20beta-yellow?style=flat-square) ![platform](https://img.shields.io/badge/platform-Windows-0078D6?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/repo-sync-tool?style=flat-square)

RepoSync is a system tray app that keeps a library of cloned Git repos fresh and visible. It updates a repo only when it can do so without losing anything. It is deliberately not a Git client.

**What's inside:**

- Add repos one at a time, or scan a parent folder for them
- Per-repo state: branch, dirty or clean, and how far ahead or behind the remote it is
- Scheduled checks, with quiet hours
- Updates that are either fetch-only or a fast-forward-only pull
- Repos that fail three times in a row are paused, not retried forever
- Colored labels, an activity log, and GitHub release and pull request counts

**Status:** public beta. The current build is a pre-release with an unsigned Windows installer, so expect a SmartScreen warning. Windows is supported and used daily. macOS is experimental and unsupported.

### [audiobook-organizer](https://github.com/prisant-labs/audiobook-organizer)

![status](https://img.shields.io/badge/status-alpha-red?style=flat-square) ![releases](https://img.shields.io/badge/releases-none%20yet-lightgrey?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/prisant-labs/audiobook-organizer?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/audiobook-organizer?style=flat-square)

Scan a messy audiobook library, understand what's in it, and rehearse a tidy-up before anything moves. It works alongside Audiobookshelf rather than replacing it.

**What's inside:**

- A library scan that sorts items into tidy books, loose files, messy names, box sets, bundles, duplicates, and empty folders
- A dry-run plan you can review, rehearsed in memory before anything touches the disk
- A self-contained HTML report you can export and share

**Status:** in progress, not a finished tool. Scanning and rehearsing is a working alpha. Applying real changes isn't a complete loop yet. There are no releases or installers, so build it from source on Windows.

---

## 3D print models

### [3d-cable-box-parametric-openscad](https://github.com/prisant-labs/3d-cable-box-parametric-openscad)

![release](https://img.shields.io/github/v/release/prisant-labs/3d-cable-box-parametric-openscad?label=stable&style=flat-square) ![next](https://img.shields.io/github/v/release/prisant-labs/3d-cable-box-parametric-openscad?include_prereleases&label=next&color=orange&style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/3d-cable-box-parametric-openscad?style=flat-square)

A parametric cable management box for 3D printing. Print a preset as-is, or open it in OpenSCAD and shape it to your desk.

**What's inside:**

- Configurable openings on each wall, an optional wrap post, interior stabilizer fins, and floor cutouts
- Optional Gridfinity interfaces
- A slicing mode that splits the box to fit your print bed, then joins the pieces with tab or snap-fit seams
- Nine ready-made presets with STLs, and a validation suite covering 65 scenarios

**Status:** v1 is the stable release, and v2 is at the release-candidate stage. You don't need any software to print a preset STL. To customize a box, you need OpenSCAD 2021.01 or later with the BOSL2 library, or the standalone bundle attached to each release.

---

Each project carries its own license: MIT for most, Apache-2.0 for obsidian-tag-visibility. Issues and pull requests are welcome in each project's own repository.
