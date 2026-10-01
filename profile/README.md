<a id="readme-top"></a>

<div align="center">

# Prisant Labs

**Tailored tools for people who tinker or live in their editors, agents, and file systems.**

<p>
  <img src="https://img.shields.io/badge/maintainer-%40jprisant-orange?style=flat-square" alt="Maintainer: @jprisant">
</p>

</div>

Prisant Labs is where [@jprisant](https://github.com/jprisant) tinkers, experiments, and publishes tools built first for personal daily use, then hardened for everyone else. Most of it is local-first, runs natively on Windows, and is built to leave your files alone unless you tell it otherwise. Tools for product managers live in the sibling org, [Product on Purpose](https://github.com/product-on-purpose).

Version badges on this page update themselves. Everything else is written by hand, including a plain status line for each project.

**Status**

- 🟢 **Stable:** 1.0 or later, or a live service
- 🟡 **Beta:** released, but not yet 1.0
- 🟠 **Pre-release:** no release yet, so you build from source
- 🟤 **Maintenance:** works, but no longer developed

**Tags**

- 🚀 **Start here:** the best first project in its category
- 🆕 **New:** public for under 30 days
- 🧪 **Experimental:** likely to change, and its status line says how

## At a glance

### Agent tooling

- 🔧 **[prisant-utilities](#-prisant-utilities)** · 🟡 Beta · 🚀 Start here<br>Eight agent skills for session continuity, decision briefs, peer review, specs, and release planning

- 📚 **[nonfiction-studio](#-nonfiction-studio)** · 🟡 Beta · 🆕 New<br>A Claude Code plugin that takes a non-fiction book from intake interview to fact-checked manuscript

- 🚚 **[agent-workspace-tools](#-agent-workspace-tools)** · 🟠 Pre-release<br>`awt`, an offline CLI that moves a project and its Claude Code history together

- 🧩 **[agent-plugins](#-agent-plugins)** · 🟢 Stable<br>The plugin marketplace to install from


### Knowledge and writing tools

- 🔖 **[obsidian-tag-visibility](#-obsidian-tag-visibility)** · 🟢 Stable · 🚀 Start here<br>Hide and flag noisy tags across a vault without editing notes

- 📦 **[obsidian-vault-collection](#-obsidian-vault-collection)** · 🟢 Stable<br>Answer-keyed test vaults and starter vaults for PKM methods and roles

- 📑 **[typora-plugin-outline-view](#-typora-plugin-outline-view)** · 🟡 Beta · 🚀 Start here · 🆕 New<br>A synchronized outline in Typora's right dock

- ⭐ **[typora-plugin-favorite-folders-files](#-typora-plugin-favorite-folders-files)** · 🟡 Beta · 🆕 New<br>Favorite folders and Markdown files one click away in Typora


### Desktop utilities

- 🔄 **[repo-sync-tool](#-repo-sync-tool)** · 🟡 Beta · 🚀 Start here<br>A tray app that keeps cloned repos fresh without touching your work

- 🎧 **[audiobook-organizer](#-audiobook-organizer)** · 🟠 Pre-release<br>Scan an audiobook library and rehearse a tidy-up before anything moves


### 3D print models

- 🔌 **[3d-cable-box-parametric-openscad](#-3d-cable-box-parametric-openscad)** · 🟢 Stable · 🚀 Start here<br>A parametric cable box with bed slicing and snap-fit seams

- 🌱 **[3d-yard-spike-parametric-openscad](#-3d-yard-spike-parametric-openscad)** · 🟠 Pre-release · 🆕 New<br>A parametric ground spike for posts and tubing that prints without supports


---

## 🤖 Agent tooling

For people who work with Claude Code or Codex every day. New here? Start with [prisant-utilities](#-prisant-utilities).

### 🔧 [prisant-utilities](https://github.com/prisant-labs/prisant-utilities)

*🟡 Beta · 🚀 Start here · Claude Code and Codex*

![release](https://img.shields.io/github/v/release/prisant-labs/prisant-utilities?display_name=tag&style=flat-square) ![marketplace pin](https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/prisant-labs/agent-plugins/main/.claude-plugin/marketplace.json&query=%24.plugins%5B1%5D.version&label=marketplace&prefix=v&color=blue&style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/prisant-utilities?style=flat-square)

```
/plugin marketplace add prisant-labs/agent-plugins
/plugin install prisant-utilities@prisant-labs
```

Pick up tomorrow exactly where today's agent session stopped. These skills cover the work around the work. They close a session cleanly, turn raw thinking into a decision, and carry a feature from spec to a taggable release.

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
- [v0.5.3](https://github.com/prisant-labs/prisant-utilities/releases/tag/v0.5.3) (Sep 2026): The skills no longer send you to a plugin that ships separately. A release-plan check that named a command you might not have now names a template that ships with the skills.

**Status:** actively released, with frequent point releases. The marketplace sometimes pins one release behind the latest.

---

### 📚 [nonfiction-studio](https://github.com/prisant-labs/nonfiction-studio)

*🟡 Beta · 🆕 New · Claude Code*

![release](https://img.shields.io/github/v/release/prisant-labs/nonfiction-studio?display_name=tag&style=flat-square) ![marketplace pin](https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/prisant-labs/agent-plugins/main/.claude-plugin/marketplace.json&query=%24.plugins%5B0%5D.version&label=marketplace&prefix=v&color=blue&style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/nonfiction-studio?style=flat-square)

```
/plugin marketplace add prisant-labs/agent-plugins
/plugin install nonfiction-studio@prisant-labs
```

Write a non-fiction book with Claude without losing track of what is true. Specialist subagents draft, every factual claim is tied to a source or marked unverified, and a quality gate decides when a chapter is done.

**What's inside:** a Claude Code plugin with 14 skills, 8 subagents, and 9 command-line engines.

- An intake interview that captures your book's thesis, audience, and voice, with the voice measured from your own writing
- Research that builds an evidence ledger, and drafting that anchors every factual claim to it or tags it `[UNVERIFIED]`
- An adversarial fact-check pass, and a seven-check quality gate you can also run by hand
- Endnotes, a bibliography, and index candidates generated from the evidence ledger
- An AI-use disclosure log that records which agent wrote what

**Recent releases:**

- [v0.1.1](https://github.com/prisant-labs/nonfiction-studio/releases/tag/v0.1.1) (Sep 2026): Skills that run a command-line tool, such as `nfs-quick-scan` and `nfs-tour`, now work after a marketplace install. The update does not touch your book's files.
- [v0.1.0](https://github.com/prisant-labs/nonfiction-studio/releases/tag/v0.1.0) (Sep 2026): The first public release takes a book from intake interview to a fact-checked manuscript. For a first look, paste 500 to 1,000 words into `nfs-quick-scan` to get a measured voice profile.

**Status:** the core authoring workflow is complete and is tested end to end in the Claude Code CLI on Ubuntu and Windows. Cowork should work the same way but is unverified, and in claude.ai chat only the skills run. Needs Node 22.12 or later.

---

### 🚚 [agent-workspace-tools](https://github.com/prisant-labs/agent-workspace-tools)

*🟠 Pre-release · Windows*

![version on main](https://img.shields.io/badge/dynamic/toml?url=https://raw.githubusercontent.com/prisant-labs/agent-workspace-tools/main/Cargo.toml&query=%24.workspace.package.version&label=main&prefix=v&color=orange&style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/agent-workspace-tools?style=flat-square)

```bash
git clone https://github.com/prisant-labs/agent-workspace-tools.git
cd agent-workspace-tools
cargo install --path crates/awt-cli
```

Move a project folder without orphaning its Claude Code history. Claude Code keys session state to a project's path, so a plain move loses it. `awt` plans the move, applies it, verifies it, and can roll it back. It is deterministic and offline, with no LLM and no network.

**What's inside:** a Rust CLI with `doctor`, `scan`, `plan`, `apply`, `verify`, `rollback`, `list`, `archive`, `associate`, and `repair`.

**Recent changes (unreleased):**

- [v1.0.0, unreleased](https://github.com/prisant-labs/agent-workspace-tools/blob/main/CHANGELOG.md#100---unreleased): A move carries a project's transcripts, history, and plugin state with it, and rolls back automatically if verification fails. New `archive` and `associate` commands keep old history from being lost.
- [v0.1.0, never tagged](https://github.com/prisant-labs/agent-workspace-tools/blob/main/CHANGELOG.md#010---internal-milestone-not-tagged): `doctor` finds stale path references across your Claude Code install, and `scan` shows everything stored for one project. Both only read, and neither writes.

**Status:** in active development. v1.0 is feature-complete but not yet tagged, so for now you build it from source with Rust. Windows only.

---

### 🧩 [agent-plugins](https://github.com/prisant-labs/agent-plugins)

*🟢 Stable · Marketplace · Claude Code*

![plugins listed](https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/prisant-labs/agent-plugins/main/.claude-plugin/marketplace.json&query=%24.plugins.length&label=plugins%20listed&color=blue&style=flat-square) ![last commit](https://img.shields.io/github/last-commit/prisant-labs/agent-plugins?style=flat-square)

```
/plugin marketplace add prisant-labs/agent-plugins
```

Add one marketplace, and every Prisant Labs plugin becomes a one-line install, including future ones.

**What's inside:** only the catalog. There's a single `marketplace.json`, and each plugin keeps its own repository, versions, and issues.

**Recent catalog changes:**

- [Sep 25, 2026](https://github.com/prisant-labs/agent-plugins/blob/main/CHANGELOG.md#2026-09-25): [nonfiction-studio](https://github.com/prisant-labs/nonfiction-studio) moved to v0.1.1, which lets its command-line skills find their own tools after a marketplace install. Run `/plugin update nonfiction-studio@prisant-labs` to get it.
- [Sep 24, 2026](https://github.com/prisant-labs/agent-plugins/blob/main/CHANGELOG.md#2026-09-24): nonfiction-studio became installable with `/plugin install nonfiction-studio@prisant-labs`, now that its repository is public.
- [Aug 28, 2026](https://github.com/prisant-labs/agent-plugins/blob/main/CHANGELOG.md#2026-08-28): prisant-utilities moved to v0.5.0, so `plab-spec` and `plab-release-plan` start when you ask for them in plain words.

**Status:** live. Both listed plugins, prisant-utilities and nonfiction-studio, install now.

---

## 📝 Knowledge and writing tools

For Obsidian and Typora users. New here? Obsidian users can start with [obsidian-tag-visibility](#-obsidian-tag-visibility), and Typora users with [Outline View](#-typora-plugin-outline-view).

### 🔖 [obsidian-tag-visibility](https://github.com/prisant-labs/obsidian-tag-visibility)

*🟢 Stable · 🚀 Start here · Obsidian desktop and mobile*

![release](https://img.shields.io/github/v/release/prisant-labs/obsidian-tag-visibility?display_name=tag&style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/obsidian-tag-visibility?style=flat-square)

**Get it:** install the BRAT plugin, choose **Add Beta Plugin**, and enter `https://github.com/prisant-labs/obsidian-tag-visibility`.

Hide, flag, and surface noisy tags across your whole vault without modifying a single note.

**What's inside:**

- A dockable Tag Visibility panel that can open beside the tag pane
- Four scopes you switch on separately: tag pane, Notebook Navigator, Properties, and autocomplete
- Per-tag always-show and always-hide overrides
- Five built-in presets, plus custom regex, frequency, and list rules
- A panic command that turns everything off at once

**Recent releases:**

- [1.0.2](https://github.com/prisant-labs/obsidian-tag-visibility/releases/tag/1.0.2) (Jul 2026): Release files now carry GitHub attestations, so you can verify that a download was built from this repository. Numeric tags in frontmatter are now indexed like any other tag.
- [1.0.0](https://github.com/prisant-labs/obsidian-tag-visibility/releases/tag/1.0.0) (Jul 2026): The first stable release adds reviewed marks and an Unreviewed filter, so you can work down a large tag set like an inbox. Hiding is display-only, so Dataview, Tasks, and Bases still see every tag.

**Status:** v1.0 has shipped, with v1.1 and v1.2 planned. It isn't in Obsidian's plugin directory yet, so for now you install it with BRAT or manually. Works on desktop and on mobile.

---

### 📦 [obsidian-vault-collection](https://github.com/prisant-labs/obsidian-vault-collection)

*🟢 Stable · Obsidian 1.9.10 or later*

![release](https://img.shields.io/github/v/release/prisant-labs/obsidian-vault-collection?display_name=tag&style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/obsidian-vault-collection?style=flat-square)

**Get it:** download any vault as a zip from the [latest release](https://github.com/prisant-labs/obsidian-vault-collection/releases/latest), then open the unzipped folder as a vault in Obsidian.

Try a note-taking method before you commit to it, or test a plugin against a vault whose right answers are known in advance.

**What's inside:** twelve vaults in three families.

- **Testing vaults:** four deterministic vaults of 20, 200, 2,000, and 20,000 notes. Each has an answer key, so a plugin's output can be checked against known truth.
- **Method vaults:** hand-authored starters for PARA, Zettelkasten, Maps of Content, and GTD.
- **Role vaults:** starters for a student, a writer, a researcher, and a software developer.

**Recent releases:**

- [v1.0.0](https://github.com/prisant-labs/obsidian-vault-collection/releases/tag/v1.0.0) (Jul 2026): The vault layout and download paths are now stable under semantic versioning. Folder names gained a `-vaults` suffix, so update any older `degit` commands.
- [v0.3.0](https://github.com/prisant-labs/obsidian-vault-collection/releases/tag/v0.3.0) (Jul 2026): Four role starter vaults arrived, for a student, a writer, a researcher, and a software developer. Each includes a saved Bases view for a query that role runs.
- [v0.2.0](https://github.com/prisant-labs/obsidian-vault-collection/releases/tag/v0.2.0) (Jul 2026): Four method starter vaults arrived, for PARA, Zettelkasten, Maps of Content, and GTD. Each has a start-here note, worked examples, templates, and a cited source.

**Status:** stable since 1.0.0, and still adding vaults.

---

### 📑 [typora-plugin-outline-view](https://github.com/prisant-labs/typora-plugin-outline-view)

*🟡 Beta · 🚀 Start here · 🆕 New · Typora on Windows and macOS*

![release](https://img.shields.io/github/v/release/prisant-labs/typora-plugin-outline-view?display_name=tag&style=flat-square) ![version on main](https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/prisant-labs/typora-plugin-outline-view/main/src/manifest.json&query=%24.version&label=main&prefix=v&color=orange&style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/typora-plugin-outline-view?style=flat-square)

**Get it:** in Community Plugin settings, open **Marketplace** and search for **Outline View**.

Keep the Files panel open and still navigate by heading. Outline View puts a synchronized heading outline in Typora's right dock.

**What's inside:**

- A live H1 to H6 outline with click navigation, which follows the heading you're on
- Heading-range selection by drag, click, or keyboard
- A choice of selector styles, plus styling for each heading level
- Commands to toggle, refresh, expand all, and collapse all

**Recent releases:**

- [0.3.1](https://github.com/prisant-labs/typora-plugin-outline-view/releases/tag/0.3.1) (Sep 2026): The settings window now shows your installed version beside the latest published one, plus a button that opens the plugin's local folder.
- [0.3.0](https://github.com/prisant-labs/typora-plugin-outline-view/releases/tag/0.3.0) (Sep 2026): Long outlines are easier to scan, with optional hierarchy guides and alternating row colors. A clickable current-path bar and a focus mode help you keep your place.
- [0.2.1](https://github.com/prisant-labs/typora-plugin-outline-view/releases/tag/0.2.1) (Sep 2026): The first public release puts a live heading outline in Typora's right dock, so the Files panel can stay open. You can select heading ranges and style each heading level.

**Status:** listed in Typora's Community Plugin marketplace. Supports Windows and macOS, and needs Community Plugin 2.10.21 or later.

---

### ⭐ [typora-plugin-favorite-folders-files](https://github.com/prisant-labs/typora-plugin-favorite-folders-files)

*🟡 Beta · 🆕 New · Typora on Windows and macOS*

![release](https://img.shields.io/github/v/release/prisant-labs/typora-plugin-favorite-folders-files?display_name=tag&style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/typora-plugin-favorite-folders-files?style=flat-square)

**Get it:** in Typora's **Plugin Marketplace**, search for **Favorites**, install it, and enable it under **Installed Plugins**.

Reach your favorite folders and Markdown files in one click. Favorites adds a Typora sidebar panel for them, alongside Typora's own Recent list.

**What's inside:**

- Favorites for files and folders, organized into groups, with Undo when you remove one
- A live, read-only view of Typora's Recent list, split into Files and Folders tabs (Windows)
- Tabbed or stacked layouts, custom, A to Z, or recently opened sorting, and search across names and paths
- Click to open, Ctrl+click for a new window, and reveal in Explorer or Finder
- Nothing on disk is ever moved, renamed, or deleted, and nothing is sent over the network

**Recent releases:**

- [0.1.1](https://github.com/prisant-labs/typora-plugin-favorite-folders-files/releases/tag/0.1.1) (Sep 2026): On Windows, the Recent list now sorts files and folders together by date. As a result, the Recently opened sort order works again.
- [0.1.0](https://github.com/prisant-labs/typora-plugin-favorite-folders-files/releases/tag/0.1.0) (Sep 2026): The first public release lets you save favorite files and folders, group them, and undo a removal. Search finds favorites and recent items by name or path.

**Status:** an early release. Windows is the development platform, where it has been installed and used, though its full native test checklist is still in progress. macOS is supported but not yet tested natively, and the Recent list is Windows only. Needs Community Plugin 2.10.21 or later.

---

## 💻 Desktop utilities

Local-first Windows desktop apps built with Rust and Tauri. New here? Start with [repo-sync-tool](#-repo-sync-tool).

### 🔄 [repo-sync-tool](https://github.com/prisant-labs/repo-sync-tool)

*🟡 Beta · 🚀 Start here · Windows*

![release](https://img.shields.io/github/v/release/prisant-labs/repo-sync-tool?display_name=tag&include_prereleases&style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/repo-sync-tool?style=flat-square)

**Get it:** download the Windows installer from the [Releases page](https://github.com/prisant-labs/repo-sync-tool/releases). Expect a SmartScreen warning, because the installer is unsigned.

Keep a whole library of cloned repos fresh without risking your work. RepoSync is a system tray app that updates a repo only when it can do so without losing anything. It is deliberately not a Git client.

**What's inside:**

- Add repos one at a time, or scan a parent folder for them
- Per-repo state: branch, dirty or clean, and how far ahead or behind the remote it is
- Scheduled checks, with quiet hours
- Updates that are either fetch-only or a fast-forward-only pull
- Repos that fail three times in a row are paused, not retried forever
- Colored labels, an activity log, and GitHub release and pull request counts

**Recent releases:**

- [v0.9.0](https://github.com/prisant-labs/repo-sync-tool/releases/tag/v0.9.0) (Jul 2026): The first release adds a tray menu that checks every repo at once, pauses all scheduled checks, and reopens recent repos. It also opens any repo's folder, terminal, editor, or GitHub page.

**Status:** public beta. The current build is a pre-release with an unsigned Windows installer. Windows is supported and used daily. macOS is experimental and unsupported.

---

### 🎧 [audiobook-organizer](https://github.com/prisant-labs/audiobook-organizer)

*🟠 Pre-release · Windows*

![last commit](https://img.shields.io/github/last-commit/prisant-labs/audiobook-organizer?style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/audiobook-organizer?style=flat-square)

```bash
git clone https://github.com/prisant-labs/audiobook-organizer.git
cd audiobook-organizer
pnpm install
pnpm tauri dev
```

See what is wrong with a messy audiobook library, and rehearse the tidy-up before anything moves. It works alongside Audiobookshelf rather than replacing it.

**What's inside:**

- A library scan that sorts items into tidy books, loose files, messy names, box sets, bundles, duplicates, and empty folders
- A dry-run plan you can review, rehearsed in memory before anything touches the disk
- A self-contained HTML report you can export and share

**Recent changes (unreleased):**

- [v0.6.0, unreleased](https://github.com/prisant-labs/audiobook-organizer/blob/main/CHANGELOG.md#060---unreleased): A Duplicates screen compares copies byte by byte when you ask. It also finds copies when a book is split across many files.
- [v0.5.0, unreleased](https://github.com/prisant-labs/audiobook-organizer/blob/main/CHANGELOG.md#050---unreleased): The engine behind real changes arrived. It journals every change before acting, can undo a run fully or partly, and never deletes an audio file.
- [v0.4.0, unreleased](https://github.com/prisant-labs/audiobook-organizer/blob/main/CHANGELOG.md#040---unreleased): The app gained its main screens, including a library home with covers and a plan preview that explains each change. You approve, reject, or defer each group of changes.

**Status:** an alpha, not a finished tool. Scanning and rehearsing work today. Applying real changes isn't a complete loop yet. There are no releases or installers, so build it from source on Windows, following [RUNNING.md](https://github.com/prisant-labs/audiobook-organizer/blob/main/RUNNING.md) for the prerequisites.

---

## 🧱 3D print models

Parametric models you can print as they are or reshape in OpenSCAD. New here? Start with the [cable box](#-3d-cable-box-parametric-openscad).

### 🔌 [3d-cable-box-parametric-openscad](https://github.com/prisant-labs/3d-cable-box-parametric-openscad)

*🟢 Stable · 🚀 Start here · OpenSCAD with BOSL2*

![release](https://img.shields.io/github/v/release/prisant-labs/3d-cable-box-parametric-openscad?display_name=tag&label=stable&style=flat-square) ![next](https://img.shields.io/github/v/release/prisant-labs/3d-cable-box-parametric-openscad?display_name=tag&include_prereleases&label=next&color=orange&style=flat-square) ![license](https://img.shields.io/github/license/prisant-labs/3d-cable-box-parametric-openscad?style=flat-square)

**Get it:** download a preset STL from the [`library/` folder](https://github.com/prisant-labs/3d-cable-box-parametric-openscad/tree/main/library) or the [Releases page](https://github.com/prisant-labs/3d-cable-box-parametric-openscad/releases). You need nothing beyond your slicer.

Hide a desk's cable clutter in a box sized to your own setup. Print a preset as it is, or open it in OpenSCAD and shape it to your desk.

**What's inside:**

- Configurable openings on each wall, an optional wrap post, interior stabilizer fins, and floor cutouts
- Optional Gridfinity interfaces
- A slicing mode that splits the box to fit your print bed, then joins the pieces with tab or snap-fit seams
- Nine ready-made presets with STLs, and a validation suite covering 65 scenarios

**Recent releases:**

- [v2.0.0-rc.3](https://github.com/prisant-labs/3d-cable-box-parametric-openscad/releases/tag/v2.0.0-rc.3) (Aug 2026, release candidate): Side openings now start 5 mm above the floor, and `All_Openings_Up=0` restores the old shape. Magnetic lid retention, an edge fillet and chamfer, and a lid-removal relief are new opt-in options.
- [v1.4.1](https://github.com/prisant-labs/3d-cable-box-parametric-openscad/releases/tag/v1.4.1) (Aug 2026): All nine presets now live in one file, so pressing F3 in OpenSCAD lists them in the Customizer dropdown. Three preset configs that failed to load now work.
- [v1.4.0](https://github.com/prisant-labs/3d-cable-box-parametric-openscad/releases/tag/v1.4.0) (Aug 2026): Sliced boxes can join with snap-fit clips that flex to absorb print error. A missing BOSL2 library now stops with one clear message instead of an empty render.

**Status:** v1 is the stable release, and v2 is at the release-candidate stage. To customize a box, you need OpenSCAD 2021.01 or later with the BOSL2 library, or the standalone bundle attached to each release.

---

### 🌱 [3d-yard-spike-parametric-openscad](https://github.com/prisant-labs/3d-yard-spike-parametric-openscad)

*🟠 Pre-release · 🆕 New · OpenSCAD with BOSL2*

![last commit](https://img.shields.io/github/last-commit/prisant-labs/3d-yard-spike-parametric-openscad?style=flat-square) ![license](https://img.shields.io/badge/license-CC%20BY--NC%204.0-lightgrey?style=flat-square)

```bash
git clone https://github.com/prisant-labs/3d-yard-spike-parametric-openscad.git
cd 3d-yard-spike-parametric-openscad
openscad yard-spike-parametric.scad
```

Stake down signs, solar lights, and garden markers with a spike that fits your post or tubing. With one setting on, it prints standing up with no supports and no bridges.

**What's inside:**

- A square or round connector, a solid spike or 2 to 16 spines, and cone, ogive, or chisel tips
- Retention options: a tie band, grip rings, and a cross hole for a screw
- A support-free mode that leaves no face overhanging past 45 degrees
- Five saved presets, from a slip-fit square post to a heavy-duty spike for rocky ground
- A verification script that renders 29 configurations and measures each mesh

**Recent changes (unreleased):**

- [v5, untagged](https://github.com/prisant-labs/3d-yard-spike-parametric-openscad/blob/main/README.md#v5): Support-free mode leaves no face steeper than 45 degrees, so the spike prints standing up without supports. Five saved presets load automatically in OpenSCAD.
- [v4, untagged](https://github.com/prisant-labs/3d-yard-spike-parametric-openscad/blob/main/README.md#v4): Spine count, thickness, and angle became adjustable, and cone, ogive, and chisel tips arrived. The model now scales with its connector size.
- [v3, untagged](https://github.com/prisant-labs/3d-yard-spike-parametric-openscad/blob/main/README.md#v3): A tie band, grip rings, and a screw hole hold the spike in its post. Bad settings now fail with a readable message.

**Status:** no releases yet. You need OpenSCAD 2021.01 or later with the BOSL2 library, or you can upload the `.scad` to MakerWorld's Parametric Model Maker. All 29 test configurations pass on both of OpenSCAD's geometry engines.

---

Each project carries its own license: MIT for most, Apache-2.0 for obsidian-tag-visibility, and CC BY-NC 4.0 for 3d-yard-spike-parametric-openscad, which remixes a non-commercial design. Issues and pull requests are welcome in each project's own repository.

<div align="center">

Built and maintained by **Jonathan Prisant**, a product leader in church technology who gets unreasonably excited about solving problems, serving people, and designing elegant systems.

[@jprisant](https://github.com/jprisant) · Sibling org: [Product on Purpose](https://github.com/product-on-purpose), open-source tools for product managers and the AI agents working alongside them

</div>

<div align="right"><a href="#readme-top">Back to top ↑</a></div>
