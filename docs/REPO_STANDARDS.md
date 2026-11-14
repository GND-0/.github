# Repository Standards

Every repository in the GND-0 org follows these standards, so anyone can open any repo and find their way around.

## Naming

`<prefix>-<short-name>` in **lowercase-kebab-case**.

| Prefix | For | Example |
|---|---|---|
| `rtl-` | Digital design projects | `rtl-riscv-rv32i`, `rtl-uart` |
| `dv-` | Verification environments / VIPs | `dv-axi-lite-vip` |
| `pd-` | Physical design flows, hardening runs | `pd-sky130-uart-harden` |
| `analog-` | Analog / custom designs | `analog-two-stage-opamp` |
| `fpga-` | FPGA demos and board support | `fpga-vga-demo` |
| `tt-` | Tiny Tapeout / tapeout submissions | `tt-gnd0-2027` |
| `learn-` | Tutorials, lab series, course material | `learn-verilog-labs` |
| `event-` | Hackathons and workshop material | `event-hackathon-2026` |
| `infra-` / `web-` | Website, tooling, automation | `web-site`, `web-sanity-studio` |

> Existing repos (`VLSI_WEB`, `VLSI-CLUB-SANITY`) predate this standard. Renaming them is optional: GitHub redirects old URLs, but you'd need to update the Vercel/Sanity integrations.

## Required in every repo

| Item | Notes |
|---|---|
| `README.md` | What it is, block diagram, how to run (sim/lint/build), status, maintainers, contributors |
| `LICENSE` | See below. No license means nobody can legally reuse the work. |
| Description and topics | Set on the repo page. Topics: domain (`rtl`, `verification`, `physical-design`, `analog`, `fpga`, `learning`, `website`) plus tech (`verilog`, `systemverilog`, `cocotb`, `sky130`, `librelane`...) |
| `.gitignore` | Must exclude build output, waveforms, flow `runs/`, `.env*` |
| CI | GitHub Actions running at least lint + tests (hardware repos get this from the template) |
| Ruleset on `main` | PR required, 1 approval, no force-push, no deletion, CI must pass |
| Maintainer | At least one, listed in [MAINTAINERS.md](MAINTAINERS.md) |

Community health files (Code of Conduct, Contributing, Security, Support, issue and PR templates) are **inherited automatically** from [`GND-0/.github`](https://github.com/GND-0/.github). Only add them to a repo if it needs something different.

## Licensing

| Content | Recommended license |
|---|---|
| RTL, testbenches, scripts, software | **Apache-2.0** (patent grant, industry-friendly) or **MIT** |
| Hardware designs you want to stay open | **CERN-OHL-S-2.0** (strongly reciprocal) or **CERN-OHL-W-2.0** (weakly reciprocal) |
| Tutorials, docs, slides | **CC-BY-4.0** |
| Club website | MIT (current) |

Never relicense other people's code. Keep their headers and `LICENSE` files in `third_party/`.

## Hardware repo layout

Use [`rtl-project-template`](https://github.com/GND-0/rtl-project-template):

```text
rtl/        synthesisable source, one module per file
tb/         testbenches (SV or cocotb)
docs/       spec, block diagrams, waveforms (images)
constraints/  SDC / FPGA pin constraints
flow/       LibreLane / FPGA flow configs (no runs/)
Makefile    lint, sim, synth, clean
```

## Releases

- Tag meaningful milestones (`v0.1.0`) with [SemVer](https://semver.org/) and write release notes.
- Attach large generated artefacts (GDS, bitstreams, PDFs) to **Releases**, not to Git history.
- Use **Git LFS** only if binaries truly must live in the repo; GitHub's free LFS quota is small.

## Lifecycle

| Stage | Meaning | Badge in README |
|---|---|---|
| 🌱 **Incubating** | Approved, early development | `status-incubating` |
| ✅ **Active** | Working, maintained, open to contributions | `status-active` |
| 🧊 **Maintenance** | Stable; bug fixes only | `status-maintenance` |
| 📦 **Archived** | No maintainer for 6 months; read-only | GitHub archive |

Badge snippet: `![status](https://img.shields.io/badge/status-active-brightgreen)`
