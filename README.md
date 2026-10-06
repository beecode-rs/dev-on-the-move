<h1 align="center">Beehive</h1>

<div align="center">
  <img src="resource/hero/beehive-hero.svg" width="360" alt="Animated beehive — a honeycomb of glowing cells with data flowing between them" />
  <br />
  <img src="https://img.shields.io/badge/status-placeholder-lightgrey" alt="Placeholder badge" />
  <img src="https://img.shields.io/badge/license-MIT-green" alt="License badge" />
  <br />
  <br />
  Made by <img src="resource/brand/beecode-logo.png" width="22" alt="Beecode logo" /> <a href="https://beecode.rs"><strong>Beecode</strong></a>
</div>

The hub of the [Beecode](https://beecode.rs) tool ecosystem: a set of small, sharply
focused apps built around one workflow — **developing on the move, with the laptop left
behind**. The pocket apps are the core of that workflow; a couple of the tools live on
the laptop too — Tmux Companion to keep tmux sessions ready for the phone to take over,
and Text Lantern, a desktop app through and through.

> This repository is a directory, not a codebase. Each tool lives in its own repo;
everything open source is public under the
[beecode-rs](https://github.com/beecode-rs) organization.

## The apps

| App | What it does |
|---|---|
| <img src="https://raw.githubusercontent.com/beecode-rs/usage-pulse/main/resource/icon/app-icon.png" width="40" alt="Usage Pulse icon" /><br>**[Usage Pulse](https://github.com/beecode-rs/usage-pulse)**<br><sub>Desktop (Electron)</sub> | Watches your coding-plan usage limits for Claude Code and z.ai GLM plans (the 5-hour window as a ring, the weekly or monthly window as a bar), lists every running Claude Code session — local and over SSH — and schedules tiny prompts timed to open fresh 5-hour windows that together cover a whole workday. |
| <img src="https://raw.githubusercontent.com/beecode-rs/relay/main/resource/icon/app-icon.png" width="40" alt="Relay icon" /><br>**[Relay](https://github.com/beecode-rs/relay)**<br><sub>Mobile (Expo, Android & iOS)</sub> | An SSH terminal in your pocket: manage a list of servers, connect, and drive a remote shell — e.g. Claude Code in tmux — from your phone. |
| <img src="https://raw.githubusercontent.com/beecode-rs/text-lantern/main/resource/icon.png" width="40" alt="Text Lantern icon" /><br>**[Text Lantern](https://github.com/beecode-rs/text-lantern)**<br><sub>Menu bar (Electron)</sub> | Reads the currently selected text aloud, fully on-device, through Piper neural voices (Serbian and English shipped, any other addable) and Kokoro. A laptop/desktop app rather than part of the mobile workflow — but a mobile version is planned. |
| <img src="https://raw.githubusercontent.com/beecode-rs/turnstone/main/resource/app-image/app-icon.png" width="40" alt="Turnstone icon" /><br>**[Turnstone](https://github.com/beecode-rs/turnstone)**<br><sub>Mobile (Expo, Android)</sub> | Browses and reads files on a remote server over SSH, strictly read-only: file tree, syntax-highlighted code, rendered Markdown and HTML, PDF, remote search, git status and diffs, and live watching of remote changes. |
| <img src="https://raw.githubusercontent.com/beecode-rs/usage-pulse-mobile/main/resource/expo-icons/icon.png" width="40" alt="Usage Pulse Mobile icon" /><br>**[Usage Pulse Mobile](https://github.com/beecode-rs/usage-pulse-mobile)**<br><sub>Mobile (Expo)</sub> | A read-only companion for Usage Pulse: the same usage and session dashboard on your phone over the VPN, plus local notifications when a session finishes or a usage warning fires. |
| <img src="https://raw.githubusercontent.com/beecode-rs/tmux-companion/main/resource/app-icon.png" width="40" alt="Tmux Companion icon" /><br>**[Tmux Companion](https://github.com/beecode-rs/tmux-companion)**<br><sub>Desktop (Electron)</sub> | Manages tmux sessions across the local machine and SSH hosts: suffixed per-app sessions, an embedded terminal running your real tmux, and one-click launches into an OS terminal. A desktop app, but a necessary part of the on-the-move workflow: it shares its session naming with Relay, so the sessions you set up here are exactly the ones you continue on the phone. |

## The idea: development without the laptop

The dev machine stays at home, on the desk, doing the heavy lifting. You walk away with
just a phone. A VPN ([Tailscale](https://tailscale.com) — or anything else that gives
IP-level reachability) makes the machine addressable from anywhere, and from there the
phone is the workstation:

- **Claude Code (or any terminal app) runs on the dev machine, inside tmux** — sessions
  survive disconnects, so a coding session started from the couch continues on the train.
- **Mobile development (Expo) works end to end** — dev servers, builds and logs are all
  reachable through the tunnel.
- **Browser apps work the same way** — the dev server runs at home, and any device on
  the VPN opens it.
- **The one limitation is desktop (Electron) apps** — there is no screen around to watch
  them on. The Claude Code session building them can still be monitored and controlled
  from the phone; only live visual testing has to wait until you are back at the desk.

## How it fits together

```mermaid
flowchart LR
    subgraph pocket["In your pocket"]
        relay["Relay — SSH terminal"]
        turnstone["Turnstone — read-only file browser"]
        upm["Usage Pulse Mobile — dashboard"]
    end
    subgraph desk["On the desk, at home"]
        tmux["tmux — Claude Code sessions"]
        up["Usage Pulse — limits & scheduling"]
        tc["Tmux Companion — desktop sidekick"]
    end
    relay -- "SSH" --> tmux
    turnstone -- "SFTP (read-only)" --> desk
    upm -- "HTTP & WebSocket" --> up
    tc -. "shares sessions" .- tmux
```

Every connection rides the VPN — the dev machine is never exposed to the open internet.

## Built the clean way

Every project in the hive is written in TypeScript and follows the
**[writing-clean-ts](https://github.com/beecode-rs/claude-skills/tree/main/skills/writing-clean-ts)**
conventions — layered patterns for services, repositories, DALs, entities, controllers,
and React components. The skill is open source too, in the
[beecode-rs](https://github.com/beecode-rs) space.

## More to come

The hive is growing. More small tools are in the works — for the pocket and for the
desk, a mobile version of Text Lantern among them — watch this repo or the
[beecode-rs organization](https://github.com/orgs/beecode-rs/repositories?type=source)
to see them land.
