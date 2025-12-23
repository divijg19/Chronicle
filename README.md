# Chronicle

> **A local-first, event-sourced decision & execution journal for developers.**

Chronicle captures not just *what* you did—but **why** you did it.

It is an append-only, time-aware personal ledger for developers who want to preserve context, reasoning, and evolution across projects.

---

## Why Chronicle?

Code remembers *changes*.  
Task managers remember *intent*.  
Logs remember *events*.

**None remember reasoning.**

After weeks or months, developers inevitably ask:

- *Why did we choose this approach?*
- *What problem was this solving?*
- *What alternatives were rejected?*
- *What changed my mind?*

Chronicle exists to answer those questions—locally, permanently, and without friction.

---

## What Is Chronicle?

Chronicle is a **local-first CLI + TUI tool** that records developer actions as immutable events and lets you replay, inspect, and query your personal development history across time.

Think:

> **Git + journaling + event sourcing — for humans.**

---

## Core Principles

- **Local-first** — No cloud, no accounts, no telemetry
- **Append-only** — History is immutable
- **Time-aware** — State can be reconstructed at any point
- **Low-friction** — Designed to be used daily
- **Human-centric** — Built for reasoning, not metrics

---

## Key Features

### 🧾 Event-Sourced Timeline
All interactions are stored as immutable events:
- decisions
- notes
- experiments
- outcomes
- commands (optional)

Every event is timestamped and replayable.

---

### ⚡ Chronicle CLI
Minimal, expressive commands:

```bash
chronicle log "Refactored auth middleware"
chronicle decide "Use Go instead of Node for websocket server"
chronicle note "Latency dropped after removing Redis"
chronicle timeline --last 7d
````

---

### 🧠 Time-Travel Introspection

Ask questions of the past:

```bash
chronicle why auth
chronicle state --at 2025-01-10
```

Chronicle reconstructs:

* decisions made
* notes taken
* relevant events
* project context at that moment

---

### 📁 Project-Scoped Journals

Chronicles are automatically scoped per project:

```
~/.chronicle/
├── nargis/
├── rig/
├── camellia/
└── global/
```

No manual setup required.

---

### 🖥️ Optional TUI (Terminal UI)

An interactive timeline built with a Go TUI stack:

* vertical chronological view
* filter by event type
* fuzzy search
* collapsible days

---

### 🔗 Git Integration (Optional)

Chronicle can:

* associate events with commits
* run via git hooks
* annotate decisions near code changes

---

## Example Event

```json
{
  "id": "evt_20250302_2141",
  "timestamp": "2025-03-02T21:41:00Z",
  "type": "decision",
  "project": "nargis",
  "context": "backend",
  "content": "Switched from Redis to Postgres due to durability concerns"
}
```

---

## Architecture Overview

* **Language:** Go
* **Storage:** SQLite or BadgerDB
* **Model:** Event sourcing (append-only log)
* **Interfaces:** CLI (default), TUI (optional)
* **Scope:** Per-project, local-only

Chronicle intentionally avoids:

* mutable state
* remote sync
* proprietary formats

---

## Installation

> Chronicle is currently in active development.

Once released:

```bash
go install github.com/divijg19/chronicle@latest
```

Or download a prebuilt binary from Releases.

---

## Development Status

| Area              | Status |
| ----------------- | ------ |
| Core event model  | ✅      |
| CLI logging       | ✅      |
| Timeline queries  | 🚧     |
| Time-travel state | 🚧     |
| TUI               | ⏳      |
| Git hooks         | ⏳      |

---

## Roadmap

### v0.1

* append-only event store
* CLI logging & querying
* project scoping
* markdown export

### v0.2

* TUI timeline
* git integration
* structured decisions

### v0.3+

* AI summarization (local / optional)
* decision embeddings
* knowledge graph export

---

## Philosophy

Chronicle treats **developer cognition** as a first-class artifact.

Building developer understanding is compounding on your choices, and Chronicle seeks to preserve this.

---

## Non-Goals

Chronicle is **not**:

* a task manager
* a note-taking app
* a replacement for Git
* a cloud service

It complements existing tools—it does not replace them.

---

## Contributing

Chronicle is opinionated by design, but contributions are welcome.

Before contributing:

* understand the local-first philosophy
* respect immutability
* avoid feature creep

Open an issue to discuss major changes.

---

Built to integrate into my systems.
