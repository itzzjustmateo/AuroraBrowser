# TODO — Aurora Browser Roadmap
Future-only. Completed work (reorg, PKGBUILD, docs, workflows, logo) is intentionally omitted.

> Legend: `- [ ] **Title** — Why (1 sentence). *AC: hint*` · Triage with `enhancement` / `good first issue`.
> Horizons: **Next (v2.1)** = high priority · **Mid (v2.2–2.3)** = queued · **Future (v3+)** = exploratory.
> Contributing: pick unchecked item → open issue → link checkbox in PR → CI must pass.

---

## 1. Product — Core Browsing UX
_Tabs, navigation, and session primitives that differentiate Aurora._

- [ ] **Vertical Tabs** — Reduce horizontal crowding for power users with many tabs. *AC: sidebar toggle, persists per window, keyboard shortcut.*
- [ ] **Built-in Ad-Block Toggle** — Offer privacy without requiring extensions. *AC: per-site toggle, filter lists, persists across restarts.*
- [ ] **Reading Mode** — Distraction-free article view for long reads and a11y. *AC: clean DOM extract, font scaling, per-domain memory.*
- [ ] **Quick Command Palette (Ctrl+K)** — Unified fuzzy search for commands, tabs, and actions. *AC: <100ms open, extensible registry.*
- [ ] **Session Manager** — Save and restore named window sessions. *AC: save/load/delete UI, JSON persist, crash restore.*
- [ ] **Onboarding Tour** — First-run guide to set search and shortcuts. *AC: 4-step overlay, skip, only on fresh profile.*

## 2. Engine & Updates — Chromium Lifecycle
_Trusted, fast, and recoverable engine updates._

- [ ] **Signed Updates via minisign** — Verify `update.sh` payloads before execution. *AC: detached .minisig, pubkey pinned, rotation docs.*
- [ ] **Delta Updates** — Ship binary diffs to cut download size. *AC: bsdiff/xdelta, fallback to full, checksum gate.*
- [ ] **Rollback UI** — Revert to previous engine with one click. *AC: lists last good version, confirm dialog, restarts cleanly.*
- [ ] **Engine Pinning per Channel (stable/beta/canary)** — Test without destabilizing daily use. *AC: channel file, parallel lanes, switch cmd.*
- [ ] **Update Changelog Toast** — Surface what's new after engine bump. *AC: toast on next launch, links to GitHub release notes.*

## 3. Packaging & Distribution — Where Users Install
_One-line installs on every platform with signed artifacts._

- [ ] **Flatpak / Flathub** — Sandboxed Linux distribution with auto-updates. *AC: flatpak-builder manifest, Flathub lint passes.*
- [ ] **Windows MSI + AzureSignTool** — Trusted installer without SmartScreen warning. *AC: WiX MSI, CI code-sign, silent install.*
- [ ] **macOS Notarization + Staple + Sparkle** — Gatekeeper-clean auto-updates on Mac. *AC: notarytool, staple, Sparkle appcast.*
- [ ] **AUR Auto-Publish via CI** — Publish on tag without manual push. *AC: deploy key, version sync check, PKGBUILD lint.*
- [ ] **Homebrew Cask** — `brew install --cask aurora-browser` for devs. *AC: Cask in homebrew-cask, CI version bump test.*

## 4. Extension & UI — Personalization & Portability
_Make new-tab feel native, accessible, and migratable._

- [ ] **i18n (de/en/es)** — Localize new-tab and settings for core audiences. *AC: i18next, JSON bundles, locale switcher + fallback en.*
- [ ] **Accessibility Audit (axe)** — Reach WCAG 2.1 AA on all UI. *AC: axe-core in CI, 0 critical violations, keyboard nav.*
- [ ] **OS Theme Sync (`prefers-color-scheme`)** — Follow system dark/light automatically. *AC: media query listener, manual override persists.*
- [ ] **Custom Search Provider UI** — Add/edit search engines inline. *AC: template URL validation, default picker, reorder.*
- [ ] **Import from Chrome/Firefox** — One-click migration of bookmarks and history. *AC: HTML/JSON picker, dedup, progress bar.*
- [ ] **Shortcut Folders & Drag-Drop** — Organize new-tab shortcuts like bookmarks. *AC: nested folders, dnd reorder, persist.*

## 5. DevEx & QA — Velocity with Safety
_Reproducible builds and fast feedback loops._

- [ ] **Vitest for Extension** — Unit test new-tab logic and utils. *AC: vitest.config.ts, >70% branch coverage, CI.*
- [ ] **Playwright for Launch Wrappers** — E2E `launch.sh` across distros. *AC: matrix Ubuntu/Fedora, trace on fail, screenshots.*
- [ ] **shellcheck + shfmt in CI** — Lint every shell script on PR. *AC: workflow job, fail on warnings, autofix suggestion.*
- [ ] **Nix Flake for Reproducible Builds** — Bit-identical artifacts anywhere. *AC: flake.nix, `nix build` reproducible, docs.*

## 6. Security & Privacy — Hardened Defaults
_Least privilege and verifiable supply chain._

- [ ] **CSP Hardening for New Tab** — Remove `unsafe-inline` from new-tab page. *AC: nonce/hash policy, no remote script, CI audit.*
- [ ] **Manifest Permission Audit** — Document and minimize permissions. *AC: table in docs, drop unused, CI diff on manifest.json.*
- [ ] **SBOM Generation (syft)** — Attach supply-chain inventory per release. *AC: syft JSON + SPDX, uploaded to GitHub release.*

## 7. Infrastructure — Docs & Releases
_Public docs, observability, and streamlined publishing._

- [ ] **Docs Site (VitePress)** — Versioned docs at `/docs` with search. *AC: VitePress, deploys on push to main, search.*
- [ ] **Privacy-Preserving Telemetry (Opt-In)** — Understand usage without tracking. *AC: opt-in modal, anonymized, no PII, toggle.*
- [ ] **Crash Reporter (Opt-In)** — Collect renderer crashes with consent. *AC: minidump upload, opt-in, 30d retention, privacy note.*
- [ ] **Auto Version-Bump Script** — Sync VERSION + package.json + manifest in one command. *AC: `scripts/bump.sh 2.1.0` updates 4 files, CI check.*

---

### Horizons & Labels
- Next (v2.1): Product palette + vertical tabs, signed updates, CSP, Vitest, VitePress.
- Mid (v2.2–2.3): Flatpak/Homebrew, i18n/a11y, delta updates, Playwright, SBOM.
- Future (v3+): Engine channels, MSI/Sparkle notarization, telemetry/crash opt-in, Nix flake.

> Tip: keep PRs small — one checkbox per PR. Add `good first issue` for isolated items.

---
Last updated: 2026-09-04 • Track issues via GitHub labels `enhancement`, `good first issue`.
