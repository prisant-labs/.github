# Prisant Labs

**Tailored tools for people who tinker or live in their editors, agents, and file systems.**

Prisant Labs is where [@jprisant](https://github.com/jprisant) tinkers, experiments, and publishes tools built first for personal daily use, then hardened for everyone else. Most of it is local-first, runs natively on Windows, and is built to leave your files alone unless you tell it otherwise.

Version badges on this page update themselves. Status lines are written by hand and say plainly how far along each project is.

## At a glance

**[Agent tooling](#agent-tooling)**

- [prisant-utilities](#prisant-utilities) - eight agent skills for session continuity, decision briefs, peer review, specs, and release planning · *active*
- [nonfiction-studio](#nonfiction-studio) - a Claude Code plugin that takes a non-fiction book from intake interview to fact-checked manuscript · *pre-1.0*
- [agent-workspace-tools](#agent-workspace-tools) - `awt`, an offline CLI that moves a project and its Claude Code history together · *pre-release*
- [agent-plugins](#agent-plugins) - the plugin marketplace to install from · *live*

**[Knowledge and writing tools](#knowledge-and-writing-tools)**

- [obsidian-tag-visibility](#obsidian-tag-visibility) - hide and flag noisy tags across a vault without editing notes · *stable*
- [obsidian-vault-collection](#obsidian-vault-collection) - answer-keyed test vaults and starter vaults for PKM methods and roles · *stable*
- [typora-plugin-outline-view](#typora-plugin-outline-view) - a synchronized outline in Typora's right dock · *released*
- [typora-plugin-favorite-folders-files](#typora-plugin-favorite-folders-files) - favorite folders and Markdown files one click away in Typora · *early release*

**[Desktop utilities](#desktop-utilities)**

- [repo-sync-tool](#repo-sync-tool) - a tray app that keeps cloned repos fresh without touching your work · *public beta*
- [audiobook-organizer](#audiobook-organizer) - scan an audiobook library and rehearse a tidy-up before anything moves · *alpha*

**[3d print models](#3d-print-models)**

- [3d-cable-box-parametric-openscad](#3d-cable-box-parametric-openscad) - a parametric cable box with bed slicing and snap-fit seams · *stable, v2 in RC*
- [3d-yard-spike-parametric-openscad](#3d-yard-spike-parametric-openscad) - a parametric ground spike for posts and tubing that prints without supports · *no releases yet*

---

## Agent tooling

For people who work with Claude Code or Codex every day.

### [prisant-utilities](https://github.com/prisant-labs/prisant-utilities)

![release](https://img.shields.io/github/v/release/prisant-labs/prisant-utilities?style=flat-square) ![marketplace pin](https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/prisant-labs/agent-plugins/main/.claude-plugin/marketplace.json&query=%24.plugins%5B1%5D.version&label=marketplace&prefix=v&color=blue&style=flat-square) ![status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/prisant-utilities?style=flat-square)

Agent skills for the work around the work: closing a session so tomorrow can pick it up, turning raw thinking into a decision, and carrying a feature from spec to a taggable release.

**What's inside:** eight skills, all prefixed `plab-`, for Claude Code and Codex.

- `plab-wrap-session` and `plab-continue-session`: a matched pair that writes a structured session log, then resumes from it
- `plab-strategy-brief`: turns a brain dump into a decision-ready analysis
- `plab-guide`: builds a guide bundle (Markdown, an ADHD-formatted variant, a quick-reference HTML page, and a short PDF)
- `plab-ai-review`: runs a structured peer review of a document with a second model
- `plab-spec` and `plab-release-plan`: numbered, source-cited acceptance criteria, then a release plan that gates the tag
- `plab-init-project`: scaffolds agent infrastructure into a repo (manual invocation only)

**Recent releases:**

- [v0.5.5](https://github.com/prisant-labs/prisant-utilities/releases/tag/v0.5.5) (Sep 2026): When you resume a session, `plab-continue-session` shows the next action as readable text instead of printing the whole continuation prompt as raw markdown.
- [v0.5.4](https://github.com/prisant-labs/prisant-utilities/releases/tag/v0.5.4) (Sep 2026): Deep session logs from `plab-wrap-session` now list what the session was least sure of, and what it saw that you may not have.
- [v0.5.0](https://github.com/prisant-labs/prisant-utilities/releases/tag/v0.5.0) (Aug 2026): `plab-spec` and `plab-release-plan` now start when you ask in plain words, such as "write the spec", so you no longer need the slash command.

**Status:** actively released, with frequent point releases. Installs from the Prisant Labs marketplace, which sometimes pins one release behind the latest.

### [nonfiction-studio](https://github.com/prisant-labs/nonfiction-studio)

![release](https://img.shields.io/github/v/release/prisant-labs/nonfiction-studio?style=flat-square) ![status](https://img.shields.io/badge/status-pre--1.0-orange?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/nonfiction-studio?style=flat-square)

Nonfiction Studio turns Claude into a governed studio for writing a non-fiction book. Specialist subagents draft, your book's facts live in plain Markdown files you own, and a deterministic quality gate decides when a chapter is done.

**What's inside:** a Claude Code plugin with 14 skills, 8 subagents, and 9 command-line engines.

- An intake interview that captures your book's thesis, audience, and voice, with the voice measured from your own writing
- Research that builds an evidence ledger, and drafting that anchors every factual claim to it or tags it `[UNVERIFIED]`
- An adversarial fact-check pass, and a seven-check quality gate you can also run by hand
- Endnotes, a bibliography, and index candidates generated from the evidence ledger
- An AI-use disclosure log that records which agent wrote what

**Recent releases:**

- [v0.1.1](https://github.com/prisant-labs/nonfiction-studio/releases/tag/v0.1.1) (Sep 2026): Skills that run a command-line tool, such as `nfs-quick-scan` and `nfs-tour`, now work after a marketplace install. The update does not touch your book's files.
- [v0.1.0](https://github.com/prisant-labs/nonfiction-studio/releases/tag/v0.1.0) (Sep 2026): The first public release takes a book from intake interview to a fact-checked manuscript with endnotes, a bibliography, and index candidates.
- [v0.1.0](https://github.com/prisant-labs/nonfiction-studio/releases/tag/v0.1.0) (Sep 2026): Paste 500 to 1,000 words into `nfs-quick-scan` to get a measured voice profile and a list of claims that need a source, with no project setup.

**Status:** pre-1.0. The core authoring workflow is complete and is tested end to end in the Claude Code CLI on Ubuntu and Windows. Cowork should work the same way but is unverified, and in claude.ai chat only the skills run. Installs from the Prisant Labs marketplace and needs Node 22.12 or later.

### [agent-workspace-tools](https://github.com/prisant-labs/agent-workspace-tools)

![version on main](https://img.shields.io/badge/dynamic/toml?url=https://raw.githubusercontent.com/prisant-labs/agent-workspace-tools/main/Cargo.toml&query=%24.workspace.package.version&label=main&prefix=v&color=orange&style=flat-square) ![status](https://img.shields.io/badge/status-pre--release-orange?style=flat-square) ![platform](https://img.shields.io/badge/platform-Windows-0078D6?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/agent-workspace-tools?style=flat-square)

`awt` moves a project folder and brings its Claude Code history with it. Claude Code keys session state to a project's path, so a plain move orphans it. `awt` plans the move, applies it, verifies it, and can roll it back. Deterministic and offline: no LLM, no network.

**What's inside:** a Rust CLI with `doctor`, `scan`, `plan`, `apply`, `verify`, `rollback`, `list`, `archive`, `associate`, and `repair`.

**Recent changes (unreleased):**

- [v1.0.0, unreleased](https://github.com/prisant-labs/agent-workspace-tools/blob/main/CHANGELOG.md#100---unreleased): A move now carries a project's transcripts, history, and plugin state with it. Every run takes a snapshot first and rolls back automatically if verification fails.
- [v1.0.0, unreleased](https://github.com/prisant-labs/agent-workspace-tools/blob/main/CHANGELOG.md#100---unreleased): `archive` copies transcripts before Claude Code's 30-day auto-delete removes them. `associate` reversibly re-links a retired project's history to a new path.
- [v1.0.0, unreleased](https://github.com/prisant-labs/agent-workspace-tools/blob/main/CHANGELOG.md#100---unreleased): Unsafe moves, such as one onto an existing folder or across drives, are refused before anything is written. Each refusal explains why and what to do next.

**Status:** pre-release, in active development. v1.0 is feature-complete but not yet tagged, so for now you build it from source with `cargo install`. Windows only.

### [agent-plugins](https://github.com/prisant-labs/agent-plugins)

![plugins listed](https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/prisant-labs/agent-plugins/main/.claude-plugin/marketplace.json&query=%24.plugins.length&label=plugins%20listed&color=blue&style=flat-square) ![last commit](https://img.shields.io/github/last-commit/prisant-labs/agent-plugins?style=flat-square)

The Prisant Labs plugin marketplace. Add it once and every plugin published here becomes available, including future ones.

```
/plugin marketplace add prisant-labs/agent-plugins
/plugin install prisant-utilities@prisant-labs
```

**What's inside:** only the catalog. There's a single `marketplace.json`, and each plugin keeps its own repository, versions, and issues.

**Recent catalog changes:**

- [Sep 25, 2026](https://github.com/prisant-labs/agent-plugins/blob/main/CHANGELOG.md#2026-09-25): [nonfiction-studio](https://github.com/prisant-labs/nonfiction-studio) moved to v0.1.1, which lets its command-line skills find their own tools after a marketplace install. Run `/plugin update nonfiction-studio@prisant-labs` to get it.
- [Sep 24, 2026](https://github.com/prisant-labs/agent-plugins/blob/main/CHANGELOG.md#2026-09-24): nonfiction-studio became installable with `/plugin install nonfiction-studio@prisant-labs`, now that its repository is public.
- [Aug 26, 2026](https://github.com/prisant-labs/agent-plugins/blob/main/CHANGELOG.md#2026-08-26): The marketplace was renamed from `agent-plugins` to `prisant-labs`. An install registered under the old name must be removed and reinstalled.

**Status:** live. Both listed plugins, prisant-utilities and nonfiction-studio, install now.

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

**Recent releases:**

- [1.0.2](https://github.com/prisant-labs/obsidian-tag-visibility/releases/tag/1.0.2) (Jul 2026): Release files now carry GitHub attestations, so you can verify that a download was built from this repository. Numeric tags in frontmatter are now indexed like any other tag.
- [1.0.0](https://github.com/prisant-labs/obsidian-tag-visibility/releases/tag/1.0.0) (Jul 2026): You can mark tags as reviewed and filter to the unreviewed ones, so a large tag set can be worked down like an inbox.
- [1.0.0](https://github.com/prisant-labs/obsidian-tag-visibility/releases/tag/1.0.0) (Jul 2026): Hiding is display-only, so Dataview, Tasks, and Bases still see every tag. Uninstalling the plugin restores every tag everywhere at once.

**Status:** v1.0 has shipped, with v1.1 and v1.2 planned. It isn't in Obsidian's plugin directory yet, so for now you install it with BRAT or manually. Works on desktop and on mobile.

### [obsidian-vault-collection](https://github.com/prisant-labs/obsidian-vault-collection)

![release](https://img.shields.io/github/v/release/prisant-labs/obsidian-vault-collection?style=flat-square) ![status](https://img.shields.io/badge/status-stable-brightgreen?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/obsidian-vault-collection?style=flat-square)

Ready-made Obsidian vaults: some for testing plugins, some for trying out a note-taking method before you commit to it.

**What's inside:** twelve vaults in three families.

- **Testing vaults:** four deterministic vaults of 20, 200, 2,000, and 20,000 notes. Each has an answer key, so a plugin's output can be checked against known truth.
- **Method vaults:** hand-authored starters for PARA, Zettelkasten, Maps of Content, and GTD.
- **Role vaults:** starters for a student, a writer, a researcher, and a software developer.

**Recent releases:**

- [v1.0.0](https://github.com/prisant-labs/obsidian-vault-collection/releases/tag/v1.0.0) (Jul 2026): The vault layout and download paths are now stable under semantic versioning. Folder names gained a `-vaults` suffix, so update any older `degit` commands.
- [v1.0.0](https://github.com/prisant-labs/obsidian-vault-collection/releases/tag/v1.0.0) (Jul 2026): A release now publishes only after every validation check passes. Its privacy scan also checks saved views, canvases, and code blocks for real contact details.
- [v0.3.0](https://github.com/prisant-labs/obsidian-vault-collection/releases/tag/v0.3.0) (Jul 2026): Four role starter vaults arrived, for a student, a writer, a researcher, and a software developer. Each includes a saved Bases view for a query that role runs.

**Status:** stable since 1.0.0, and still adding vaults. Download a single vault as a zip from Releases. Needs Obsidian 1.9.10 or later.

### [typora-plugin-outline-view](https://github.com/prisant-labs/typora-plugin-outline-view)

![release](https://img.shields.io/github/v/release/prisant-labs/typora-plugin-outline-view?style=flat-square) ![version on main](https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/prisant-labs/typora-plugin-outline-view/main/src/manifest.json&query=%24.version&label=main&prefix=v&color=orange&style=flat-square) ![platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS-555?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/typora-plugin-outline-view?style=flat-square)

Outline View puts a synchronized heading outline in Typora's right dock, so the Files panel can stay open on the left.

**What's inside:**

- A live H1 to H6 outline with click navigation, which follows the heading you're on
- Heading-range selection by drag, click, or keyboard
- A choice of selector styles, plus styling for each heading level
- Commands to toggle, refresh, expand all, and collapse all

**Recent releases:**

- [0.3.1](https://github.com/prisant-labs/typora-plugin-outline-view/releases/tag/0.3.1) (Sep 2026): The settings window now shows your installed version beside the latest published one, plus a button that opens the plugin's local folder.
- [0.3.0](https://github.com/prisant-labs/typora-plugin-outline-view/releases/tag/0.3.0) (Sep 2026): Long outlines are easier to scan, with optional hierarchy guides and alternating row colors. Both accept custom colors for light and dark themes.
- [0.3.0](https://github.com/prisant-labs/typora-plugin-outline-view/releases/tag/0.3.0) (Sep 2026): A clickable current-path bar and a focus mode for the current branch help you keep your place. Formatted headings no longer show their markdown markers.

**Status:** 0.3.1 is released and listed in Typora's Community Plugin marketplace. Supports Windows and macOS.

### [typora-plugin-favorite-folders-files](https://github.com/prisant-labs/typora-plugin-favorite-folders-files)

![release](https://img.shields.io/github/v/release/prisant-labs/typora-plugin-favorite-folders-files?style=flat-square) ![status](https://img.shields.io/badge/status-early%20release-yellow?style=flat-square) ![platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS-555?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/typora-plugin-favorite-folders-files?style=flat-square)

Favorites keeps your favorite folders and Markdown files one click away in a Typora sidebar panel, alongside Typora's own Recent list.

**What's inside:**

- Favorites for files and folders, organized into groups, with Undo when you remove one
- A live, read-only view of Typora's Recent list, split into Files and Folders tabs (Windows)
- Tabbed or stacked layouts, custom, A to Z, or recently opened sorting, and search across names and paths
- Click to open, Ctrl+click for a new window, and reveal in Explorer or Finder
- Nothing on disk is ever moved, renamed, or deleted, and nothing is sent over the network

**Recent releases:**

- [0.1.1](https://github.com/prisant-labs/typora-plugin-favorite-folders-files/releases/tag/0.1.1) (Sep 2026): On Windows, the Recent list now sorts files and folders together by date. As a result, the Recently opened sort order works again.
- [0.1.0](https://github.com/prisant-labs/typora-plugin-favorite-folders-files/releases/tag/0.1.0) (Sep 2026): The first public release lets you save favorite files and folders, organize them into groups, and undo a removal.
- [0.1.0](https://github.com/prisant-labs/typora-plugin-favorite-folders-files/releases/tag/0.1.0) (Sep 2026): Search finds favorites and recent items by name or path. On Windows, Ctrl+click opens one in a new Typora window.

**Status:** early release, installable from Typora's Plugin Marketplace. Windows is the development platform, where it has been installed and used, though its full native test checklist is still in progress. macOS is supported but not yet tested natively, and the Recent list is Windows only. Needs Community Plugin 2.10.21 or later.

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

**Recent releases:**

- [v0.9.0](https://github.com/prisant-labs/repo-sync-tool/releases/tag/v0.9.0) (Jul 2026): The tray menu can check every repo at once, pause or resume all scheduled checks, and reopen recent repos. Closing the window keeps RepoSync running in the tray.
- [v0.9.0](https://github.com/prisant-labs/repo-sync-tool/releases/tag/v0.9.0) (Jul 2026): You can open a repo's folder, terminal, editor, or GitHub page straight from the app.
- [v0.9.0](https://github.com/prisant-labs/repo-sync-tool/releases/tag/v0.9.0) (Jul 2026): Any repo can override the global check schedule from its detail panel, and the change takes effect immediately.

**Status:** public beta. The current build is a pre-release with an unsigned Windows installer, so expect a SmartScreen warning. Windows is supported and used daily. macOS is experimental and unsupported.

### [audiobook-organizer](https://github.com/prisant-labs/audiobook-organizer)

![status](https://img.shields.io/badge/status-alpha-red?style=flat-square) ![releases](https://img.shields.io/badge/releases-none%20yet-lightgrey?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/prisant-labs/audiobook-organizer?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/audiobook-organizer?style=flat-square)

Scan a messy audiobook library, understand what's in it, and rehearse a tidy-up before anything moves. It works alongside Audiobookshelf rather than replacing it.

**What's inside:**

- A library scan that sorts items into tidy books, loose files, messy names, box sets, bundles, duplicates, and empty folders
- A dry-run plan you can review, rehearsed in memory before anything touches the disk
- A self-contained HTML report you can export and share

**Recent changes (unreleased):**

- [v0.6.0, unreleased](https://github.com/prisant-labs/audiobook-organizer/blob/main/CHANGELOG.md#060---unreleased): A new Duplicates screen compares copies byte by byte when you ask, with progress you can stop. It keeps every comparison it finished.
- [v0.6.0, unreleased](https://github.com/prisant-labs/audiobook-organizer/blob/main/CHANGELOG.md#060---unreleased): You choose which copy to keep, and nothing moves until you confirm that group. Confirmed copies move to an Archive, and undoing the run puts them all back.
- [v0.6.0, unreleased](https://github.com/prisant-labs/audiobook-organizer/blob/main/CHANGELOG.md#060---unreleased): Duplicates are now found even when a book is split across many files, such as one copy in a single file and another in twelve MP3s.

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

**Recent releases:**

- [v2.0.0-rc.3](https://github.com/prisant-labs/3d-cable-box-parametric-openscad/releases/tag/v2.0.0-rc.3) (Aug 2026, release candidate): Side openings now start 5 mm above the floor, and `All_Openings_Up=0` restores the old shape. Magnetic lid retention, an edge fillet and chamfer, and a lid-removal relief are new opt-in options.
- [v1.4.1](https://github.com/prisant-labs/3d-cable-box-parametric-openscad/releases/tag/v1.4.1) (Aug 2026): All nine presets now live in one file, so pressing F3 in OpenSCAD lists them in the Customizer dropdown. Three preset configs that failed to load now work.
- [v1.4.0](https://github.com/prisant-labs/3d-cable-box-parametric-openscad/releases/tag/v1.4.0) (Aug 2026): Sliced boxes can join with snap-fit clips that flex to absorb print error. A missing BOSL2 library now stops with one clear message instead of an empty render.

**Status:** v1 is the stable release, and v2 is at the release-candidate stage. You don't need any software to print a preset STL. To customize a box, you need OpenSCAD 2021.01 or later with the BOSL2 library, or the standalone bundle attached to each release.

### [3d-yard-spike-parametric-openscad](https://github.com/prisant-labs/3d-yard-spike-parametric-openscad)

![releases](https://img.shields.io/badge/releases-none%20yet-lightgrey?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/prisant-labs/3d-yard-spike-parametric-openscad?style=flat-square) ![license](https://img.shields.io/badge/license-CC%20BY--NC%204.0-lightgrey?style=flat-square)

A parametric ground spike that plugs into a square post or round tubing, for staking down signs, solar lights, and garden markers. With one setting on, it prints standing up with no supports and no bridges.

**What's inside:**

- A square or round connector, a solid spike or 2 to 16 spines, and cone, ogive, or chisel tips
- Retention options: a tie band, grip rings, and a cross hole for a screw
- A support-free mode that leaves no face overhanging past 45 degrees
- Five saved presets, from a slip-fit square post to a heavy-duty spike for rocky ground
- A verification script that renders 29 configurations and measures each mesh

**Recent changes (unreleased):**

- [v5, untagged](https://github.com/prisant-labs/3d-yard-spike-parametric-openscad/blob/main/README.md#v5): Support-free mode leaves no face steeper than 45 degrees, so the spike prints standing up without supports or bridges.
- [v5, untagged](https://github.com/prisant-labs/3d-yard-spike-parametric-openscad/blob/main/README.md#v5): Five saved presets load automatically in OpenSCAD, from a slip-fit square post to a heavy-duty spike for rocky ground.
- [v5, untagged](https://github.com/prisant-labs/3d-yard-spike-parametric-openscad/blob/main/README.md#v5): Certain collar thicknesses no longer export as three separate solids, and clearance fits no longer leave an unsupported ledge.

**Status:** no releases yet, so clone the repository to use it. You need OpenSCAD 2021.01 or later with the BOSL2 library, or you can upload the `.scad` to MakerWorld's Parametric Model Maker. All 29 test configurations pass on both of OpenSCAD's geometry engines.

---

Each project carries its own license: MIT for most, Apache-2.0 for obsidian-tag-visibility, and CC BY-NC 4.0 for 3d-yard-spike-parametric-openscad, which remixes a non-commercial design. Issues and pull requests are welcome in each project's own repository.
