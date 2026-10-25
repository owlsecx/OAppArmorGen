# 🦉 OAppArmorGen

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-Security-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **OAppArmorGen** — part of the OwlSec Toolkit.

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OAppArmorGen helps you write and review AppArmor profiles. It builds profiles in correct AppArmor 3.x syntax from ready-made templates or by inspecting an ELF binary's interpreter and linked libraries. Its linter grades existing profiles and flags dangerous capabilities, overly broad rules and unconfined transitions.

---

## ✨ Features

- Profile builder with AppArmor 3.x syntax: abi, includes, capabilities, network, owner/deny path rules, signal/ptrace/unix and rlimits
- Templates: minimal, cli, network-service, python, systemd-daemon, container and strict
- Generates a profile from an ELF binary by mapping its interpreter and NEEDED libraries to abstraction includes
- Linter with a hardening grade: dangerous capabilities, complain mode, broad globs, missing denies on sensitive paths, Ux/ix risks
- Optional systemd unit hardening snippet and a capability / exec-mode reference
- Reports in TXT / JSON / Markdown / CSV / SARIF; --lint exits with code 3 on HIGH/CRITICAL findings

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OAppArmorGen                               # interactive menu
./OAppArmorGen --template network-service --attach /usr/sbin/mydaemon -o mydaemon.profile
./OAppArmorGen --binary /usr/bin/myapp --systemd
./OAppArmorGen --lint /etc/apparmor.d/usr.sbin.nginx
```

Run `./OAppArmorGen --help` for the full list of options.

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
