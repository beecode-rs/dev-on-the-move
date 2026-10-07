# README Template — Beecode Hub Projects

One README shape for every project in the
[beecode-rs](https://github.com/beecode-rs) hive. Copy everything between the
`━━━ TEMPLATE START ━━━` and `━━━ TEMPLATE END ━━━` markers into the project's
`README.md`, replace every `{{placeholder}}`, delete the instruction comments,
and delete sections the project doesn't use.

## Ground rules

1. **Audience.** The README is for **end users** — people who install and use the
   app. Anything for developers (setup details, scripts, releasing, architecture,
   deep feature explanations) lives in `resource/docs/` and is only *linked* from
   the README.
2. **Language & tone.** English, plain words, short sentences. Assume the reader
   is not a developer. Never explain internal code structure beyond one tech
   mention in the intro line.
3. **Section order is fixed.** Keep the order below; omit sections that don't
   apply, but don't reorder or rename them (heading names are anchor targets —
   other sections link to them).

## Legend — how each section is marked

| Marker | Meaning |
|---|---|
| **▣ FIXED** | Wording is mandatory and identical across **every** Beecode hub project — all projects are written by the Beecode org. Only `{{placeholder}}` values change. Do not rephrase, shorten, or extend the visible text. |
| **◈ PROJECT** | Each project writes this itself, following the given structure and rules. |
| **◇ OPTIONAL** | Include only when it applies to the project; skip it otherwise. |

Placeholder convention: `{{like-this}}`. Every placeholder must be replaced — a
shipped README containing `{{ }}` is a bug.

---

━━━ TEMPLATE START ━━━

<!-- ▣ FIXED — Header block. Icon: 140 px wide for desktop apps, 160 px for mobile.
     Keep the icon at resource/icon/app-icon.png (mobile apps may keep their
     existing resource/expo-icons/icon.png path). Badges: the four below are the
     fixed set; Expo apps add the Expo SDK badge after the platform badge.
     platform value is URL-encoded, e.g. macOS%20%7C%20Linux · Android%20%7C%20iOS
     · macOS%20%7C%20Linux%20%7C%20Windows · Android -->

<p align="center">
  <img src="{{icon-path}}" width="{{140-or-160}}" alt="{{APP_NAME}} icon" />
</p>

<h1 align="center">{{APP_NAME}}</h1>

<p align="center">
  <img src="https://img.shields.io/github/package-json/v/beecode-rs/{{repo}}?label=version" alt="Version badge" />
  <img src="https://img.shields.io/badge/status-proof%20of%20concept-orange" alt="Proof of concept badge" />
  <img src="https://img.shields.io/badge/platform-{{platforms-url-encoded}}-blue" alt="Platform badge" />
  <img src="https://img.shields.io/badge/license-MIT-green" alt="License badge" />
</p>

<!-- Expo apps only, after the platform badge:
  <img src="https://img.shields.io/badge/Expo%20SDK-{{sdk-version}}-000020" alt="Expo SDK badge" />
-->

<p align="center">
  Made by
  <a href="https://beecode.rs"><img src="resource/brand/beecode-logo.png" width="20" alt="Beecode logo" /></a>
  <a href="https://beecode.rs"><strong>Beecode</strong></a>
</p>

<!-- The Beecode logo is a local copy: copy resource/brand/beecode-logo.png from
     the dev-on-the-move hub repo into the project's own resource/brand/ and
     reference it with the relative path — never the hub's raw GitHub URL. -->

<!-- ◈ PROJECT — Intro. 2–4 sentences: what the app is (tech in one phrase, e.g.
     "a small Electron + TypeScript desktop app" / "a small Expo (React Native)
     app"), what it does, and who it is for. House style: a lead-in sentence
     ending with a colon, then "It does N things:" as bold-lead-word bullets,
     one line each. Detail goes to docs, not here. -->

{{APP_NAME}} is {{one-line-what-it-is}. It does {{N}} things:

- **{{Feature}}** — {{one sentence}}.
- **{{Feature}}** — {{one sentence}}.
- **{{Feature}}** — {{one sentence}}.

<!-- ▣ FIXED — Status section. Wording below is exact while the version is 0.x.
     When the major version moves to 1, replace the status badge above with
     https://img.shields.io/badge/status-stable-brightgreen, retitle the section
     "## Status", delete the POC paragraph, and write 2–3 plain sentences on what
     "stable" means (what is supported, what the update policy is). -->

## Status: Proof of Concept

{{APP_NAME}} is at **v{{VERSION}}** and still a proof of concept. It was built through rapid AI-assisted iteration ("vibe coding") rather than carefully reviewed engineering, so expect rough edges, missing pieces, and breaking changes without notice. While it remains a POC the version stays on `0.x`; the move out of the POC phase coincides with the major version moving to `1`.

<!-- ◈ PROJECT — Screenshots. One shape for every app, mobile or desktop:
     3-per-row table grids, title row on top, images below. Every image is
     wrapped in a click-to-fullsize link (the <a> points at the image file
     itself), width 240, with meaningful alt text. Titles are 1–3 words; a
     title whose screen has a matching docs section (typically in
     resource/docs/features.md) links to that section's anchor, a title
     without one stays plain text — the skeleton below shows both. A
     screenshot that maps to a docs section is also embedded in that section
     of the docs page — same file, referenced from resource/docs/ as
     ../screenshots/<file>, typically right under the section heading — so
     the grid is not its only home. Docs embeds always use the
     <img src="../screenshots/<file>" height="480" alt="..." /> form rather
     than ![]() — the height cap keeps portrait shots from rendering full
     column height and leaves landscape shots visually unchanged. Keep it to
     ~9 images maximum; every major screen shown, no duplicates; the last row
     may be shorter. No captions or walkthroughs in the README — what the
     controls do is docs material. The closing link sentence is fixed shape
     (adjust only the doc path); drop it only if the project has no features
     doc. -->

## Screenshots

| [{{Title}}](resource/docs/features.md#{{anchor}}) | [{{Title}}](resource/docs/features.md#{{anchor}}) | {{Title}} |
| :---: | :---: | :---: |
| <a href="resource/screenshots/{{file}}.png"><img src="resource/screenshots/{{file}}.png" width="240" alt="{{what the screen shows}}" /></a> | <a href="resource/screenshots/{{file}}.png"><img src="resource/screenshots/{{file}}.png" width="240" alt="{{what the screen shows}}" /></a> | <a href="resource/screenshots/{{file}}.png"><img src="resource/screenshots/{{file}}.png" width="240" alt="{{what the screen shows}}" /></a> |

The titles link to each feature's section in [resource/docs/features.md](resource/docs/features.md).

<!-- ◈ PROJECT — Features. Bullet list only: bold lead word + one sentence.
     No sub-headings, no settings walkthroughs. Detailed feature explanations
     (settings, edge cases, how each feature works) go to resource/docs/ —
     typically resource/docs/features.md — and the section ends with the
     link sentence below (fixed shape, adjusted only for the actual doc path).
     In that doc, a feature with a related screenshot embeds it in its section
     (from resource/docs/ that is ../screenshots/<file>, typically right
     under the heading, always as <img ... height="480"> to cap the render
     height). -->

## Features

- **{{Feature}}** — {{one sentence}}.
- **{{Feature}}** — {{one sentence}}.

For a deeper look at each feature — settings, edge cases, and how things work under the hood — see [resource/docs/features.md](resource/docs/features.md).

<!-- ◇ OPTIONAL — Why this exists. 1–2 short paragraphs of personal context when
     the app's purpose needs explaining (usage-pulse and tmux-companion have good
     examples). Skip for self-explanatory apps. Placement is fixed: right after
     Features. -->

## Why this exists

{{1–2 paragraphs — the problem the app solves, in the user's terms.}}

<!-- ◈ PROJECT — Feature status. Honest, user-relevant granularity. Never leave
     the Planned list empty — if there is nothing, write the fixed sentence
     "Nothing planned right now." -->

## Feature status

Done:

- [x] {{feature}}
- [x] {{feature}}

Planned:

- [ ] {{feature}}

<!-- ◈ PROJECT — Requirements. Two sub-lists: what the *installed app* needs
     (OS versions, runtime deps like python3 or a local tmux) and what a
     *build from source* needs (Node.js, pnpm). Omit the section entirely if
     the app has no prerequisites beyond a supported OS. -->

## Requirements

**To use the app:** {{OS versions and runtime prerequisites, or "a {{platform}} machine".}}

**To build from source:** [Node.js](https://nodejs.org) and [pnpm](https://pnpm.io){{any extra build tools}}.

<!-- ▣ FIXED — Install section. The section heading and the first sentence are
     fixed. Include only the per-OS blocks the project actually ships, in the
     order below (macOS, Linux, Windows, Android, iOS). Each block's wording is
     fixed — only placeholders and the file-name pattern change. -->

## Download & install

Downloads live on the [GitHub Releases](https://github.com/beecode-rs/{{repo}}/releases) page.

<!-- ▣ FIXED — macOS block (Electron apps shipping a dmg). -->

**macOS** (Apple Silicon & Intel, one universal build): download `{{App-Name}}-<version>-universal.dmg` and drag **{{APP_NAME}}** to Applications.

> The release builds are not signed or notarized with an Apple developer certificate, so macOS blocks the first launch. That is standard macOS behavior for any unsigned app — it needs a one-time confirmation that you trust it:
>
> 1. Open **{{APP_NAME}}** once — it will be blocked with a "cannot be checked for malicious software" dialog. Dismiss the dialog.
> 2. Go to **System Settings → Privacy & Security** and scroll down to the Security section.
> 3. Under "'{{APP_NAME}}' was blocked from use because it is not notarized", click **Open Anyway** and confirm.

Alternatively, clear the quarantine flag from a Terminal:

```bash
xattr -cr '/Applications/{{App Name}}.app'
```

<!-- ▣ FIXED — Linux block (Electron apps shipping AppImage + deb). -->

**Ubuntu — AppImage**: make it executable and run it (no install needed):

```bash
chmod +x {{App-Name}}-<version>.AppImage
./{{App-Name}}-<version>.AppImage
```

**Ubuntu — deb package**:

```bash
sudo apt install ./{{app-name}}_<version>_amd64.deb
```

<!-- ▣ FIXED — Windows block (Electron apps shipping an NSIS exe). -->

**Windows**: run `{{App-Name}}-Setup-<version>.exe`. The installer is unsigned, so SmartScreen will warn — choose **More info → Run anyway**.

<!-- ▣ FIXED — Android block (Expo apps). -->

### Android

1. Download the `{{App-Name}}-v<version>-android.apk` asset.
2. Allow installing unknown apps for your browser or file manager (Settings → Apps → Special access → Install unknown apps), then open the APK and confirm the install. Or install over USB: `adb install {{App-Name}}-v<version>-android.apk`.
3. To update, just install a newer APK over the old one — releases are signed with the same key.

<!-- ▣ FIXED — iOS block (Expo apps). -->

### iOS

The `{{App-Name}}-v<version>-ios-unsigned.ipa` asset is **unsigned** (no Apple Developer account is involved), so it gets signed with your own Apple ID at install time by a sideload tool:

- **[AltStore](https://altstore.io)**: add the IPA through AltStore (or AltServer) with your Apple ID.
- **[Sideloadly](https://sideloadly.io)**: drag the IPA in, sign with your Apple ID, install over USB.
- On devices with **TrollStore**, the unsigned IPA can be installed directly and permanently.

Caveats: with a free Apple ID the signature lasts 7 days (re-sideload to refresh) and counts against the 3-active-apps limit. {{One project-specific sentence on what a reinstall loses — e.g. where settings live.}}

<!-- ◈ PROJECT — From source. Skeleton below is fixed; fill the clone URL, the
     project's real bootstrap command (pnpm install, or pnpm run init where the
     project uses it), and its run command. Keep it to install + one run
     command — everything else lives in resource/docs/development.md. -->

### From source

Requires [Node.js](https://nodejs.org) and [pnpm](https://pnpm.io).

```bash
git clone https://github.com/beecode-rs/{{repo}}.git
cd {{repo}}
pnpm install
pnpm dev
```

{{One sentence on extra prerequisites, or delete the line.}} The full development setup lives in [resource/docs/development.md](resource/docs/development.md).

<!-- ◇ OPTIONAL — Getting started. Recommended when first use needs setup
     (pairing, installing an engine, adding a first server): 3–6 numbered steps
     from "installed" to "first success". Skip when install = use. -->

## Getting started

1. {{step}}
2. {{step}}
3. {{step}}

<!-- ▣ FIXED — Privacy & security. The core sentence below is fixed org-wide
     (fill the placeholders; keep the final clause verbatim). Add one short
     project-specific bullet or sentence after it only if the app needs more
     explaining (e.g. where tokens are stored, what a reinstall loses). -->

## Privacy & security

**{{What secrets — e.g. "Passwords, private keys, and accepted host keys"}}** stay on your device{{, stored WHERE — e.g. "in the OS secure store"}} and are sent only to {{where — e.g. "the server they belong to"}}. The app contains no analytics and no telemetry.

<!-- ▣ FIXED — Support & contributing. Exact wording. -->

## Support & contributing

Found a bug or have an idea? Open an issue on [GitHub](https://github.com/beecode-rs/{{repo}}/issues) — include the app version, your OS, and the steps to reproduce. Pull requests are welcome too; keep the [feature status](#feature-status) in mind, and open an issue before starting something large.

<!-- ▣ FIXED — For developers. Section heading and purpose are fixed; the link
     list follows the resource/docs/ convention (development.md required,
     others as they exist). This is the only place the README points
     developers at docs — keep it to links. -->

## For developers

The README covers using the app. To work on it:

- [Development setup](resource/docs/development.md) — prerequisites, daily commands, quality gates
- [Architecture](resource/docs/architecture.md) — how the source is layered
- [Releasing](resource/docs/releasing.md) — tag-driven releases

<!-- ◇ OPTIONAL — Acknowledgments. Required when the app bundles or depends on
     third-party engines, models, or assets that need credit — Text Lantern's
     GPL-3.0 piper-tts engine is the standing example (visible credit is a
     license obligation there). Plain "name — what it provides — license/link"
     lines. -->

## Acknowledgments

- {{name}} — {{what it provides}} ([license]({{link}}))

<!-- ▣ FIXED — License. Exact wording; a root LICENSE file (MIT) exists in
     every hub repo. This is always the last section. -->

## License

[MIT](LICENSE)

━━━ TEMPLATE END ━━━

---

## Writer's checklist (run before opening the PR)

- [ ] No `{{placeholder}}` left anywhere (`grep -F '{{' README.md` comes back empty).
- [ ] Version badge reads from `package.json` (it self-updates) and the Status
      paragraph names the **current** version — they must agree.
- [ ] Status is "Proof of Concept" + orange badge + fixed paragraph (version 0.x),
      or the stable form (version ≥ 1).
- [ ] Only the per-OS install blocks the project actually ships are present.
- [ ] Screenshots: 3-per-row grids of click-to-fullsize images (width 240) from
      `resource/screenshots/`, with 1–3 word titles; a title with a matching
      docs section links to it, and the section ends with the features.md link
      sentence.
- [ ] Every screenshot that maps to a feature is embedded in that feature's
      docs section too (`../screenshots/<file>` from `resource/docs/`), not
      only in the README grid, and every docs embed uses the height-capped
      form (`<img ... height="480">`).
- [ ] Every feature bullet is one sentence; detail lives in `resource/docs/`.
- [ ] Planned list is either non-empty or says "Nothing planned right now."
- [ ] The Beecode logo image loads (resource/brand/beecode-logo.png exists in the
      project — copied from the hub's resource/brand/, never the raw GitHub URL).
- [ ] All internal links work: `LICENSE`, `resource/docs/*.md`, GitHub issues/releases.
- [ ] Read top-to-bottom by a non-developer: can they tell what it does, see it,
      install it, and know where to get help — without reading source code?
