# snap-obsidian-strict

**Un-official strict Snap for Obsidian (Obsidian.md)**

This repository contains a **Snapcraft project** to build **Obsidian** — the popular knowledge-base/markdown editor — as a _strictly confined_ Snap on Linux.

> ⚠️ Obsidian’s official Snap in the Snap Store uses **classic confinement** by default (requiring `--classic` on install) due to its broad filesystem access model. This project attempts to package Obsidian in a more sandboxed, secure way via **strict confinement**. :contentReference[oaicite:1]{index=1}

---

## What This Is

This repo provides:

* A `snapcraft.yaml` that builds **Obsidian** from its release artifacts or sources  
* A Snap definition aiming for **strict confinement** so it runs in a secure sandbox  
* Interfaces declarations for limited access (e.g., files inside the user’s home via `home` plug)

Strict confinement snaps are isolated from the rest of the system unless explicit interfaces are connected. They cannot access arbitrary system resources without declaration. :contentReference[oaicite:2]{index=2}

---

## Why Strict Confinement?

By default, Obsidian’s Snap in the Snap Store requires **classic confinement** because it needs broad access to the user’s vault and files. Classic snaps behave much like traditional packages and require manual approval during publishing. :contentReference[oaicite:3]{index=3}

Strict confinement aims to:

* Restrict the application from touching the system outside of defined interfaces  
* Improve security and reduce accidental system impact  
* Ensure reproducible, sandboxed builds

**Note:** Fully strict confinement may require extra interface connections from users (e.g., `home`, `x11`, `wayland`, `desktop`).

---
