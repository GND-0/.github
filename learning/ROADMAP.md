# 🗺️ GND_0 VLSI Learning Roadmap

A structured path from "what's a flip-flop?" to "my design is on a real chip", using **free and open-source tools** wherever possible, so anyone can follow it on a laptop.

```text
 0 Foundations ─► 1 HDL ─► 2 Verification ─┬─► 3 FPGA
                                            ├─► 4 RTL-to-GDS ─► 🧩 Tapeout
                                            ├─► 5 Analog & Layout
                                            └─► 6 Architecture / RISC-V
                          7 Careers & interview prep (alongside everything)
```

**How to use this**
- Each stage has **Learn → Practice → Prove-it**. Prove-it is a small project you push to GitHub and post in *Show and Tell*.
- Stages 0–2 are the common core. After that, follow the domains you enjoy.
- Rough timings assume ~5 hours a week. Go at your own pace.
- Stuck? Ask in [Discussions → Q&A](https://github.com/orgs/GND-0/discussions/categories/q-a). Found a better resource? Open a 📚 *Learning material* issue.

> **Toolbox install (Linux / WSL2 / macOS):** the easiest all-in-one route is the [OSS CAD Suite](https://github.com/YosysHQ/oss-cad-suite-build) (Yosys, nextpnr, Icarus, Verilator, GTKWave, SymbiYosys and more in one download). Windows users: install **WSL2 + Ubuntu** first.

---

## Stage 0 · Foundations (3–4 weeks)

**Learn**
- Number systems, Boolean algebra, K-maps, combinational vs sequential logic
- Flip-flops, latches, counters, FSMs (Moore vs Mealy), setup/hold time intuition
- CMOS inverter basics: how a transistor becomes a logic gate
- Linux shell basics, Git and GitHub workflow

**Resources**
- *Digital Design and Computer Architecture* (Harris & Harris), chapters 1–3
- [Nand2Tetris](https://www.nand2tetris.org/), part 1: build a computer from NAND gates
- [NPTEL](https://nptel.ac.in/): Digital Circuits courses
- [The Missing Semester](https://missing.csail.mit.edu/) (MIT): shell, Git, editors
- [GitHub Skills](https://skills.github.com/)

**Prove-it:** fork a GND-0 repo and get one PR merged (a docs fix counts!).

---

## Stage 1 · Hardware Description Languages (4–6 weeks)

**Learn**
- Verilog: modules, `assign`, `always`, blocking vs non-blocking, parameters, `generate`
- Writing *synthesisable* code: what makes a latch, a mux, a register
- SystemVerilog for design: `logic`, `always_ff`/`always_comb`, `enum`, `struct`, packages, interfaces
- Simulation and waveforms; linting

**Tools:** Icarus Verilog · Verilator (lint + fast sim) · GTKWave or Surfer (waveforms) · [EDA Playground](https://www.edaplayground.com/) (browser-based, includes commercial simulators)

**Resources**
- [HDLBits](https://hdlbits.01xz.net/): *do all of it*. The single best Verilog practice site.
- [ChipVerify](https://www.chipverify.com/): Verilog and SystemVerilog reference
- *Digital Design and Computer Architecture*, chapter 4 (HDL)
- Sutherland & Mills, *Verilog and SystemVerilog Gotchas*: for after you've made the mistakes 🙂

**Prove-it:** create a repo from [`rtl-project-template`](https://github.com/GND-0/rtl-project-template) and build a **UART transmitter + receiver** with a self-checking testbench and passing CI.

---

## Stage 2 · Verification (4–6 weeks)

**Learn**
- Self-checking testbenches, reference models, directed vs random stimulus
- SystemVerilog assertions (SVA) and functional coverage
- **cocotb**: Python testbenches (fast to learn, used widely in open source)
- UVM architecture: agents, drivers, monitors, scoreboards, sequences
- Formal verification basics: proving properties instead of simulating them

**Tools:** cocotb · Verilator · SymbiYosys (formal) · EDA Playground for UVM

**Resources**
- [cocotb documentation](https://docs.cocotb.org/)
- [ChipVerify](https://www.chipverify.com/) UVM tutorials
- [Verification Academy](https://verificationacademy.com/) (Siemens, free registration)
- [ZipCPU blog](https://zipcpu.com/): excellent on formal verification and practical debugging

**Prove-it:** verify a **synchronous FIFO** with cocotb: random tests, a scoreboard, and coverage of full/empty corner cases. Bonus: prove "never overflows" with SymbiYosys.

---

## Stage 3 · FPGA Prototyping (3–5 weeks) — *domain track*

**Learn:** constraints (pin mapping, clocks), clock domains and synchronisers, debouncing, using on-board peripherals (LEDs, 7-seg, VGA, UART), timing reports

**Tools:** open flow, Yosys + nextpnr (iCE40, ECP5, some Gowin parts) · vendor flow, AMD Vivado / Intel Quartus (free editions) for Xilinx/Intel boards. Check the club's [hardware list](https://gnd0.vercel.app/resources) for boards you can borrow.

**Resources:** [fpga4fun](https://www.fpga4fun.com/) · [Project F](https://projectf.io/) (FPGA graphics, beginner-friendly) · [Nandland](https://nandland.com/)

**Prove-it:** a **VGA pattern generator** or **UART-controlled LED/7-seg** running on a real board, with a video in Show and Tell.

---

## Stage 4 · RTL-to-GDS / Physical Design (6–10 weeks) — *domain track*

**Learn**
- Logic synthesis, standard cells, liberty files
- Static timing analysis: setup/hold, slack, clock skew, false and multicycle paths, SDC constraints
- Floorplanning, power distribution, placement, clock-tree synthesis, routing
- Sign-off: DRC, LVS, antenna, IR drop
- What a PDK contains

**Tools (all open source)**
| Step | Tool |
|---|---|
| Synthesis | Yosys |
| STA | OpenSTA |
| Place and route | OpenROAD |
| Complete flow | **LibreLane**, the successor to OpenLane 2, maintained under the FOSSi Foundation |
| Layout / DRC / LVS | Magic, KLayout, Netgen |
| Open PDKs | SkyWater **SKY130**, GlobalFoundries **GF180MCU**, IHP **SG13G2** |

**Resources**
- [LibreLane docs](https://librelane.readthedocs.io/) (if you've seen older OpenLane tutorials, read its *Migrating from OpenLane* page)
- [OpenROAD docs](https://openroad.readthedocs.io/)
- [Zero to ASIC course](https://www.zerotoasiccourse.com/) (Matt Venn)
- [VLSI System Design (VSD)](https://www.vlsisystemdesign.com/) workshops
- *CMOS VLSI Design* (Weste & Harris)

**Prove-it:** harden your Stage 1 or 2 design through LibreLane on SKY130 or GF180 with **zero DRC/LVS errors and positive slack**. Post the layout screenshot and metrics.

### 🧩 Group tapeout: get real silicon
[Tiny Tapeout](https://tinytapeout.com/) lets you put a small design on a real chip at low cost, sharing a die with hundreds of other projects. The club runs a **Tapeout Cohort** (see [EVENTS_PLAYBOOK](../docs/EVENTS_PLAYBOOK.md)): small teams design, verify and submit together. Check the [Tiny Tapeout runs page](https://tinytapeout.com/runs) for open shuttles and deadlines. Shipping terms differ per shuttle, so read them before submitting.

---

## Stage 5 · Analog and Custom Layout (8+ weeks) — *domain track*

**Learn:** MOSFET models and regions, current mirrors, differential pairs, op-amps, comparators, bandgaps; noise and mismatch; layout matching (common-centroid, interdigitation); parasitic extraction

**Tools:** Xschem (schematic) · ngspice (simulation) · Magic / KLayout (layout) · Netgen (LVS) · SKY130 or GF180MCU or IHP SG13G2 PDK

**Resources:** Razavi, *Design of Analog CMOS Integrated Circuits* · Prof. Razavi's UCLA analog lectures (free on YouTube) · [NPTEL](https://nptel.ac.in/) analog IC design courses · IHP and SkyWater open-PDK analog tutorials

**Prove-it:** design, simulate and lay out a **two-stage op-amp** or **5-transistor OTA** with clean DRC/LVS and post-layout simulation.

---

## Stage 6 · Computer Architecture / RISC-V — *domain track*

**Learn:** ISA design, single-cycle → multi-cycle → pipelined CPU, hazards and forwarding, caches, branch prediction, bus protocols (APB, AXI-Lite, Wishbone)

**Resources:** Patterson & Hennessy, *Computer Organization and Design: RISC-V Edition* · Harris & Harris, *DDCA RISC-V Edition* · [RISC-V specifications](https://riscv.org/specifications/) · open cores to study: PicoRV32, SERV, Ibex

**Prove-it:** an **RV32I** core that passes the official [riscv-tests](https://github.com/riscv-software-src/riscv-tests) in simulation. A club flagship project candidate!

---

## Stage 7 · Careers and Interview Prep — *alongside everything*

**Core topics interviewers ask about:** digital logic puzzles, FSM design, CDC and metastability, FIFO depth calculation, STA (setup/hold fixes), Verilog gotchas, SystemVerilog OOP, UVM phases, CMOS basics, low-power techniques (clock gating, power gating)

**Do this**
- Keep your GitHub tidy: pinned repos with READMEs, diagrams and passing CI *are* your portfolio
- Contribute to real open-source hardware: [FOSSi Foundation](https://fossi-foundation.org/), [lowRISC](https://lowrisc.org/), [OpenROAD](https://github.com/The-OpenROAD-Project), [Tiny Tapeout](https://github.com/TinyTapeout)
- Club **mock interviews** with alumni mentors each semester
- Track internship and fellowship calls in Discussions → Announcements

---

## Semester plan (suggested study-circle cadence)

| Weeks | Odd semester | Even semester |
|---|---|---|
| 1–4 | Stage 0 bootcamp for 1st years | Stage 2 (cocotb + UVM) |
| 5–9 | Stage 1 + HDLBits challenge | Domain tracks (3/4/5/6) in parallel |
| 10–13 | Mini-project sprint (UART / FIFO) | Tapeout cohort / hackathon |
| 14+ | Show-and-tell demo day | Demo day + handover |

*Maintained by the Technical Lead and Domain Leads. Edit via pull request.*
