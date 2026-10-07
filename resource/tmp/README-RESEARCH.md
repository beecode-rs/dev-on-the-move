# README Research — Current State Across the Hub

Date: 2026-10-07 · Scope: the six apps listed in the hub README · Output: [`resource/template/README_template.md`](../template/README_template.md).

All six projects were surveyed by reading their `README.md` in full, plus a check of
each repo's `resource/` layout, `LICENSE`, and release links.

| Project | Type | Version stated in README | Release host | Dev docs location |
|---|---|---|---|---|
| usage-pulse | Desktop (Electron) | v0.3.0 | GitHub `beecode-rs/usage-pulse` | `resource/doc/` (singular) |
| relay | Mobile (Expo, Android & iOS) | — | GitHub `beecode-rs/relay` | `resource/docs/` |
| text-lantern | Menu bar (Electron) | v0.1.0 | **`gitea.bugarinovic.com/milos/text-lantern`** | none |
| turnstone | Mobile (Expo, Android) | — | GitHub `beecode-rs/turnstone` | `resource/docs/` **and** root `docs/` |
| usage-pulse-mobile | Mobile (Expo) | — | GitHub `beecode-rs/usage-pulse-mobile` | `resource/docs/` |
| tmux-companion | Desktop (Electron) | v0.1.0 | GitHub `beecode-rs/tmux-companion` | `resource/docs/` |

## 1. Section inventory (what each README has today)

| | UP | RE | TL | TU | UM | TC |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| Centered icon in header | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ |
| "Made by Beecode" line | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ |
| Version badge | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ |
| Status badge | PoC 🟠 | Early dev 🟡 | PoC 🟠 | Early dev 🟡 | Early dev 🟡 | PoC 🟠 |
| Platform badge | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Expo SDK badge | — | ✅ | — | ✅ | ✅ | — |
| License badge (MIT) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Status section w/ "vibe coding" paragraph | ✅ | ✅ | ✅ | ✅ | ❌ (badge only) | ✅ |
| "0.x = POC" version rule sentence | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ |
| Screenshots section | ✅ H3/screen | ✅ table | ✅ H3/screen | ✅ table | ✅ table | ✅ table |
| Feature bullets in intro | ✅ | ✅ | ✅ | ✅ | ❌ (prose) | ✅ |
| Feature-status checklist | ✅ | ✅ (empty TODO) | ✅ | ✅ | ❌ | ~ ("Todo", 1 item) |
| Install from releases, per-OS steps | ✅ | ✅ | ✅ | ~ (described only) | ✅ | ✅ |
| macOS unsigned warning + `xattr` | ✅ | — | ✅ | — | — | ✅ |
| Android APK steps (unknown apps / adb) | — | ✅ | — | ~ | ✅ | — |
| iOS sideload block (AltStore/Sideloadly/TrollStore) | — | ✅ | — | ~ | ✅ | — |
| Security/privacy statement | ~ (in Trackers) | ✅ | ✅ | ✅ | ~ (scattered) | ✅ |
| "No analytics or telemetry" claim | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ |
| Clone & run commands in README | ✅ | ❌ (in docs) | ~ (`<repo-url>` placeholder) | ❌ (in docs) | ✅ | ✅ |
| Development scripts listed inline | full | link | full | link | link | medium |
| Releasing section | ✅ | link | ✅ | ❌ | link | ❌ |
| Architecture section | ✅ link | ✅ inline | ✅ layout | ✅ link | ✅ inline | ✅ link |
| Contributing section | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ |
| Credits/acknowledgments | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| License (MIT) at the end | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## 2. Similarities — the de-facto common skeleton

Even without a template, a strong house style already exists:

1. **Header pattern** — centered app icon, centered `H1` title, centered badge row
   (status + platform + license, sometimes version / Expo SDK), optionally a
   "Made by Beecode" line.
2. **Opening formula** — "A small *{Electron + TypeScript | Expo (React Native)}* app
   that …" followed by "It does N things:" — bold-lead-word bullets, one line each.
3. **Status disclaimer** — five of six carry a near-verbatim paragraph: *built through
   rapid AI-assisted iteration ("vibe coding") rather than carefully reviewed
   engineering, expect rough edges, missing pieces, and breaking changes without
   notice.* The three PoC apps add the version rule: *while it remains a POC the
   version stays on `0.x`; leaving the POC phase coincides with the major version
   moving to `1`.*
4. **Screenshots** — every project has them, captioned, under `resource/screenshots/`
   (TL alone uses `resource/media/`).
5. **Install from releases** — per-OS subsections with practical unsigned-app guidance
   (macOS Open Anyway / `xattr`; Android unknown-apps + adb; iOS sideload tools).
   The macOS and iOS blocks are already word-for-word identical between the repos
   that have them.
6. **Feature-status checklist** — `[x]` Done / `[ ]` Planned lists.
7. **Security statement shape** — "secrets stay on the device, stored in the OS secure
   store, sent only to the server they belong to; no analytics or telemetry."
8. **Development** — Node.js + pnpm, tag-driven releases via `pnpm release:*`, CI
   quality gates; deeper material delegated to `resource/doc(s)/`.
9. **License** — `[MIT](LICENSE)` as the closing section, with a root `LICENSE` file
   in every repo (verified present in all six).

## 3. Divergences found (what the template must settle)

1. **Two status vocabularies.** "Proof of Concept" (orange; UP, TL, TC — includes the
   0.x version rule) vs "Early Development" (yellow; RE, TU, UM — no version rule).
   Decision encoded in the template: **one scale** — an app is a *proof of concept*
   while its version starts with `0.` (v0.x), and leaves the POC phase when the major
   version moves to `1`. "Early development" is retired.
2. **text-lantern is the outlier.** Releases point at a private Gitea
   (`gitea.bugarinovic.com/milos/text-lantern`), and its clone instructions still use
   a `<repo-url>` placeholder. Template standardizes on
   `https://github.com/beecode-rs/<repo>` everywhere.
3. **Docs location drift.** `resource/doc/` (UP), `resource/docs/` (RE, TU, UM, TC),
   root `docs/` (TU, mixed), none (TL). Template standardizes on **`resource/docs/`**
   with conventional filenames (`development.md`, `architecture.md`, `releasing.md`,
   `scripts.md`, `features.md`).
4. **"Made by Beecode" on only 3 of 6**, with two different logo paths
   (`resource/brand/beecode-logo.png` vs `assets/images/beecode-logo.png`).
   Template makes it a fixed block whose logo loads from the hub repo's raw URL — one canonical copy, no per-project logo files.
5. **usage-pulse-mobile is missing** the icon, the status paragraph, the feature-status
   checklist, and a contributing section. Template makes all four required.
6. **Version badge on only 2 of 6.** Template includes it in the fixed badge set
   (auto-reads `package.json`, so it never goes stale).
7. **Section order varies** — e.g. TU puts Screenshots before Status; UP buries
   install below "Why this exists" and long feature prose; TL puts Features before
   Screenshots. Template fixes one order, with install early (an end user's first
   question after the screenshots).
8. **Audience mixing.** UP, TL and RE/TU/UM carry substantial developer content inline
   (full script lists, releasing procedures, architecture internals, env-var tweaks).
   Per the hub decision, the README targets **end users**; developer material moves to
   `resource/docs/` and the README keeps a minimal *From source* + *For developers*
   link section.
9. **Checklist hygiene.** RE has an empty `TODO` heading; TU's "Planned: nothing".
   Template rule: never leave an empty Planned list — write "Nothing planned right now."
10. **Asset conventions.** Screenshot folders (`resource/screenshots` vs
    `resource/media`) and icon widths (140–160) differ. Template fixes
    `resource/screenshots/`, 160 px icons for mobile apps, 140 px for desktop.

## 4. What the template adds on open-source best-practice grounds

| New section | Why |
|---|---|
| **Requirements** (before install) | End users need runtime prerequisites up front (OS versions, `python3` for Piper's engine, tmux presence) — separate from build-from-source prerequisites. |
| **Getting started** (after install) | Answers "I installed it — now what?" (pair the phone, install the TTS engine, add a tracker). Standard README guidance: a minimal first-run path to value. |
| **Privacy & security** as a first-class, fixed-core section | These apps hold SSH keys, provider tokens and shell access; "nothing leaves your device, no analytics, no telemetry" is an org-wide guarantee worth stating identically everywhere. |
| **Support & contributing** with report-a-bug guidance | Ask for version + OS + repro steps in issues; all six welcome issues/PRs but only 4 say so, none say what to include. |
| **Acknowledgments** (optional) | Needed when bundling third-party engines/assets — TL ships GPL-3.0 `piper-tts` alongside an MIT app, which *requires* visible credit and license care. |
| **FAQ / Changelog / Code of Conduct** (deliberately not added) | Releases page already carries auto-generated notes; the org is too small for a CoC to be meaningful now. Revisit at 1.x. |

## 5. Rules encoded in the template (summary)

- **Audience split:** README = end users; everything for developers lives under
  `resource/docs/` and is linked from two short sections (*From source*, *For developers*).
- **Phase rule:** version `0.x` ⇔ status "proof of concept" (orange badge + fixed
  disclaimer paragraph); at `1.x` the badge flips to "stable" and the disclaimer is
  replaced by a short stability note.
- **Fixed blocks** (identical wording across all beecode projects, only placeholders
  change): header/badges/made-by, status disclaimer, per-OS install blocks (macOS
  unsigned, Linux AppImage/deb, Windows SmartScreen, Android APK, iOS sideload),
  privacy core sentence, support & contributing, license.
- **English, plain language, short sentences**; no internal code structure in the
  README beyond a one-line tech mention.
