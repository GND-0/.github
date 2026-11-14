# Contributing to GND_0

Thanks for helping build the VLSI community at IIIT Dharwad! This guide applies to **every repository in the GND-0 org** unless a repo has its own `CONTRIBUTING.md`.

New to Git or open source? That's fine. Read [First-time contributors](#first-time-contributors) and ask in [Discussions → Q&A](https://github.com/orgs/GND-0/discussions).

---

## Ways to contribute

You don't need to write RTL to help:

| Contribution | Examples |
|---|---|
| 🧠 **Designs** | RTL modules, FPGA demos, verification environments, physical-design runs |
| 📝 **Docs and learning material** | Tutorials, lab write-ups, fixing unclear READMEs, diagrams |
| 🐛 **Testing and review** | Reproducing bugs, adding test cases, reviewing pull requests |
| 🌐 **Website** | Features and fixes for [`VLSI_WEB`](https://github.com/GND-0/VLSI_WEB) |
| 💬 **Community** | Answering Q&A, running a study circle, mentoring juniors |

## The workflow

```text
Find or open an issue ──► get it assigned ──► branch ──► commit ──► pull request ──► review ──► merge
```

### 1. Find or open an issue
- Browse [`good first issue`](https://github.com/issues?q=org%3AGND-0+is%3Aopen+label%3A%22good+first+issue%22) and [`help wanted`](https://github.com/issues?q=org%3AGND-0+is%3Aopen+label%3A%22help+wanted%22).
- For anything non-trivial, **open an issue first** so we can agree on the approach before you invest time.
- Comment **"I'd like to work on this"** and wait for a maintainer to assign you. Claims expire after 7 days of silence.

### 2. Fork or branch
- **Outside contributors and new members:** fork the repo and work on your fork.
- **Members with write access:** create a branch in the repo.

Branch naming: `<type>/<issue-number>-<short-description>`

```text
feat/42-uart-tx-module
fix/57-fifo-full-flag-off-by-one
docs/63-openroad-install-guide
```

### 3. Commit
We use [Conventional Commits](https://www.conventionalcommits.org/):

```text
<type>(<scope>): <summary in imperative mood, ≤ 72 chars>

<optional body: what and why, not how>

Closes #42
```

| Type | Use for |
|---|---|
| `feat` | New module, feature or page |
| `fix` | Bug fix (functional or timing) |
| `test` | Testbenches, assertions, coverage |
| `docs` | Documentation only |
| `refactor` | Restructuring with no behaviour change |
| `perf` | Area, power or timing improvements |
| `build` / `ci` | Makefiles, flow configs, GitHub Actions |
| `chore` | Housekeeping |

Example: `feat(alu): add signed overflow detection`

### 4. Open a pull request
- Fill in the PR template. It asks for what changed, how you tested it, and your checklist.
- Link the issue (`Closes #42`).
- Mark the PR as **Draft** if it's not ready, which is a good way to get early feedback.
- Keep it small. Big changes should be split into a series of PRs.

### 5. Review
- Every change goes through a PR. GitHub doesn't force an approval, so authors can merge their own PRs, but **ask for at least 1 review** from a maintainer before merging anything non-trivial. Changes to rules, governance or CI should get **2** reviews.
- Maintainers may self-merge small fixes (typos, docs, broken links) without review.
- Reviewers aim to respond within **3 days**. Ping politely in the PR if it's been longer.
- Address feedback with new commits (don't force-push during review). The maintainer will **squash-merge** when ready.

## Quality bar by project type

### RTL / hardware
- [ ] Synthesisable code in `rtl/`, testbenches in `tb/` (follow [`rtl-project-template`](https://github.com/GND-0/rtl-project-template))
- [ ] `make lint` is clean (Verilator `--lint-only -Wall`) or warnings are explained
- [ ] `make sim` passes with a self-checking testbench that prints PASS/FAIL, not just waveforms
- [ ] No latches unless intentional and commented; reset behaviour documented
- [ ] Ports and parameters documented in the module header
- [ ] No proprietary PDK, library or tool files (see [Community Rules](COMMUNITY_RULES.md#-confidentiality-licensing-and-integrity-important-for-vlsi))

**Verilog/SystemVerilog style (short version)**
- `snake_case` for signals and modules, `UPPER_CASE` for parameters and `localparam`s
- Suffixes: `_n` active-low, `_q` registered, `_d` next-state, `_i` / `_o` for ports where it helps
- One module per file; the file name matches the module name
- `always_ff` / `always_comb` in SystemVerilog; non-blocking (`<=`) in sequential logic, blocking (`=`) in combinational logic
- Use `default_nettype none` at the top of every file

### Physical design
- [ ] Commit the flow config (`config.json`/`config.yaml`), constraints (SDC) and pin order, not the `runs/` directory
- [ ] Report key metrics in the PR (area, utilisation, WNS/TNS, DRC/LVS status)
- [ ] State the PDK and tool versions used

### Website (`VLSI_WEB`)
- [ ] `pnpm lint` passes; `pnpm build` passes with your `.env.local`
- [ ] Screenshots for UI changes (desktop and mobile)
- [ ] No secrets or `.env` files committed

### Docs and tutorials
- [ ] Steps tested on a fresh setup
- [ ] Tool versions stated
- [ ] Images in an `assets/` or `docs/images/` folder, compressed

## First-time contributors

1. Install Git and set up your [SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).
2. Fork the repo → `git clone` your fork → `git checkout -b docs/1-fix-typo`.
3. Make the change → `git commit -m "docs: fix typo in README"` → `git push -u origin docs/1-fix-typo`.
4. On GitHub, click **Compare & pull request**.
5. Celebrate 🎉 and post it in *Show and Tell*.

Useful practice: the [GitHub Skills](https://skills.github.com/) courses, and `good first issue` labels across the org.

## Recognition

- All contributors are listed in each repo's README (we use the [all-contributors](https://allcontributors.org/) convention).
- Notable contributions are featured on the [club website](https://gnd0.vercel.app/) and in semester reports.
- Sustained contribution is the path to becoming a maintainer ([GOVERNANCE.md](GOVERNANCE.md#becoming-a-maintainer)).

## License of contributions

By contributing, you agree that your contribution is licensed under the license of the repository you contribute to (shown in its `LICENSE` file). You confirm that you have the right to submit it. In particular, it contains no NDA, proprietary or academically restricted material.
