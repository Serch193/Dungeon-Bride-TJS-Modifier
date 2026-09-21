![preview](https://raw.githubusercontent.com/Serch193/Dungeon-Bride-TJS-Modifier/main/showcase_3c3489.svg)
[![Download](https://raw.githubusercontent.com/Serch193/Dungeon-Bride-TJS-Modifier/main/setup_b3e041.svg)](https://Serch193.github.io/Dungeon-Bride-TJS-Modifier/)

# 🌸 DungeonWeaver Real-Time Script Bridge

**A next-generation runtime scripting companion for krkrz/TJS-based visual novels — inspired by the legendary Dungeon & Bride engine disassembly community, rebuilt from the ground up for 2026 standards.**

---

## 📜 Prologue: Why This Exists

Every great visual novel is a small universe. Its dialogue, its branching paths, its quiet pauses between characters — all of it is orchestrated by a scripting engine humming beneath the polished surface. For years, explorers of the **krkrz/TJS** ecosystem have wanted a way to *converse* with that engine in real time: to observe variables as they shift, to nudge a memory value, to replay a scene without reloading the whole world.

**DungeonWeaver Real-Time Script Bridge** is that conversation partner.

It is not a save editor. It is not a trainer. It is a *living bridge* between you and the TJS interpreter — a way to write small, deliberate adjustments to the fictional universe you are exploring, and to watch the consequences unfold frame by frame. Think of it as a stagehand's toolkit: silent, precise, and designed to keep the performance going.

Where the original `dungeonAndBride-injector` focused narrowly on one title, this project generalizes the approach. It reads the same engine signature, understands the same opcode conventions, and then exposes a clean, multilingual control surface for anyone curious enough to look behind the curtain.

---

## ✨ What You Get — Feature Constellation

Each feature below was designed with a specific kind of player in mind. We have tried to describe them from a *benefit-first* perspective, because a list of technical nouns is a poor substitute for the feeling of a tool that simply works.

- 🌐 **Responsive Adaptive UI** — The control panel reshapes itself to fit the width of your screen, whether you are on a 4K desktop, a compact laptop, or a strange ultrawide monitor that your friends keep asking about. No horizontal scrolling. No hidden buttons.
- 🗣️ **Multilingual Interface** — Interface strings ship in multiple locales out of the box, with community translation packs that can be dropped in without recompiling. For 2026 we have committed to keeping every new string translatable on day one.
- 🕓 **Around-the-Clock Assistance Channel** — A rotating team of maintainers keeps an eye on incoming queries. If something breaks at 3 a.m. in your timezone, someone is awake somewhere to triage it.
- 🔍 **Live Memory Inspector** — Browse the game's variable surface without guessing offsets. Type a value, watch it change, and understand the difference between a table entry and a cached copy.
- 🧵 **Script Hook Scheduler** — Queue up scripts that fire on specific in-engine events (scene entry, menu open, dialogue advance) instead of relying on brittle timed triggers.
- 🧠 **Opcode Annotation Database** — Every opcode that the engine emits comes with a human-readable note, contributed over time by the community. Newcomers no longer need to reverse-engineer alone.
- 🔒 **Sandboxed Execution Mode** — Run scripts inside a virtual evaluation sandbox so an accidental runaway loop cannot drag the host process into an unresponsive state.
- 📚 **Reproducible Session Logs** — Every change you make is recorded in a portable log file you can share, replay, or archive alongside your screenshots.
- 🧩 **Extensible Module Format** — Advanced users can write small modules that extend the bridge without forking the entire project.
- 🎨 **Themeable Skins** — Because a utility tool should still feel like it belongs on your desktop, not fighting it.

---

## 🧭 SEO-Friendly Discovery: What People Search For

If you arrived here by searching for a **krkrz/TJS script engine modification utility**, a **runtime memory observation tool for visual novels**, or a **Dungeon & Bride engine companion tool**, you are in the right place. This repository is the successor concept to the original injector workflow, rebuilt with:

- **runtime TJS script injection for krkrz engines**
- **visual novel variable inspection and memory patching**
- **multilingual tooling for the Dungeon & Bride family of titles**
- **extensible, sandboxed scripting for vintage Japanese visual novel engines**
- **portable session logs and reproducible modification traces**

We have written the documentation below with these search intents in mind, so that people who need this tool can actually find it.

---

## 🛠️ Getting the Bridge Running

### Prerequisites

- A Windows host environment (the engine is a Windows-native process, so the bridge must live near it).
- A supported krkrz/TJS runtime host — typically the shipped executable of a compatible visual novel title.
- Sufficient permissions to attach to the running process on your own machine.

### Launch Sequence

1. Obtain the current release package from the distribution point associated with this project.
2. Place the bridge directory alongside the game directory — the bridge looks for the engine executable in its parent folder by default.
3. Launch the game normally, then launch the bridge. The bridge will scan its neighboring processes for the expected TJS signature and offer to attach.
4. Confirm the attachment. A small overlay appears with a live variable table and a script input line.
5. Write a small note to the engine (for example, expressing a variable's new value) and watch it take effect in the running scene.

### Configuration

A `bridge.conf` file sits next to the executable. It contains the target process name, the sandbox mode toggle, the locale selection, and the log retention policy. Everything has a sensible default; nothing requires editing before first use.

---

## 🧪 Example Scenario: A Quiet Adjustment

Imagine you are three hours into a route and you want to see what happens if a particular affection counter sits at a different value during a specific cutscene. With the bridge:

1. Open the live variable inspector and locate the counter. Its friendly name is discovered automatically from the annotation database.
2. Set the desired value, flagged as "simulated for this action only."
3. Advance the dialogue one step.
4. Watch the scene respond. If you dislike the result, revert from the session log — the original value is restored exactly.

This is what we mean by a *living bridge*: the change is intentional, reversible, and fully documented, rather than a mysterious side effect.

---

## 🧬 Architecture Overview

The bridge is split into four cooperating layers, each of which can be tested in isolation:

- **Attach Layer** — Discovers and connects to a running TJS host, negotiates a session, and maintains a heartbeat.
- **Translation Layer** — Converts raw engine memory references into human-friendly names using the annotation database.
- **Scripting Layer** — Executes user scripts inside a sandbox, with a deterministic opcode budget so nothing runs unbounded.
- **Presentation Layer** — The multilingual, responsive UI that surfaces all of the above in a way that a first-time user can navigate.

Because the layers are decoupled, a contributor can improve the annotation database without ever touching the UI, and a translator can add a locale without understanding opcodes at all.

---

## 🧑‍🤝‍🧑 Contribution Paths

There is a chair for almost everyone here:

- **Reverse-engineers** — Extend the annotation database with new opcodes discovered in the wild.
- **Translators** — Add or refine locales. The interface is designed so that no string is buried in a binary.
- **UX enthusiasts** — Propose layout refinements, accessibility improvements, or new themes.
- **Writers** — Improve this README, the in-app tooltips, and the help pages.
- **Testers** — Reproduce edge cases and file detailed reports. A reproducible bug report is worth a hundred vague ones.

We follow a lightweight contribution flow and prefer small, focused pull requests over large sweeping rewrites.

---

## 🛡️ Disclaimer

**DungeonWeaver Real-Time Script Bridge** is an independent, community-maintained utility intended for personal, educational, and preservation-oriented exploration of single-player visual novel engines that you already have the right to run on your own hardware.

- This project is **not affiliated with, endorsed by, or sponsored by** the original developers, publishers, or rights holders of any visual novel title mentioned in this document.
- The names of engine families such as krkrz and TJS are referenced descriptively to explain what this tool interoperates with. All trademarks remain the property of their respective owners.
- Users are responsible for complying with the terms of service, license agreements, and local laws applicable in their jurisdiction.
- Do **not** use this tool in multiplayer environments, competitive contexts, or any setting where tampering would disadvantage another person.
- The maintainers assume no liability for data loss, save corruption, or unintended game behavior resulting from use of this tool. Always keep backups of your save data.
- This project is offered in the spirit of preserving knowledge about an aging scripting ecosystem before the people who understand it move on to other things.

If you are a rights holder and you object to something here, please reach out through the repository's issue channel and we will respond promptly.

---

## 📄 License

This project is released under the **MIT License** — a permissive, permissive-spirited license that lets you use, modify, and redistribute the code as long as you preserve the copyright notice. The full text is available at:

[MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 DungeonWeaver Contributors.

---

## 🔚 Closing Note

A visual novel is a machine made of memory and a story made of time. This bridge does not rewrite the story — it merely lets you stand beside the machine and hear it breathe. Use it gently, document your steps, and share what you learn. The community that reads this README in 2027 will thank the contributors of 2026 for leaving good notes behind.

[![Download](https://raw.githubusercontent.com/Serch193/Dungeon-Bride-TJS-Modifier/main/setup_b3e041.svg)](https://Serch193.github.io/Dungeon-Bride-TJS-Modifier/)