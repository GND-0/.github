# Community Rules

These are the short, practical rules for working in GND_0 spaces. The [Code of Conduct](CODE_OF_CONDUCT.md) covers how we treat each other; this page covers how we work.

Breaking a rule usually earns a friendly reminder. Repeated or deliberate violations are handled under the Code of Conduct [enforcement ladder](CODE_OF_CONDUCT.md#enforcement).

---

## 🗣️ Communication

1. **Use the right place.**
   | You want to... | Go to |
   |---|---|
   | Ask a question or get help | Discussions → **Q&A** |
   | Propose an idea, project or event | Discussions → **Ideas** / **Project Proposals** |
   | Show something you built | Discussions → **Show and Tell** |
   | Report a bug or request a change in a repo | That repo's **Issues** |
   | Announce something official | Discussions → **Announcements** (Core Team only) |
2. **Search first.** Your question may already have an answer. Link to it if it's related.
3. **Ask good questions.** Say what you're trying to do, what you tried, and the exact error. Paste code and logs as text in code blocks, not screenshots of a screen.
4. **English in public spaces** so everyone (including alumni and outside contributors) can follow. Casual chat groups can use any language.
5. **No spam or unrelated self-promotion.** Sharing your own VLSI project, blog or article is welcome in *Show and Tell*.
6. **Don't DM maintainers for support.** Ask in public so the answer helps the next person too.

## 🔒 Confidentiality, licensing and integrity (important for VLSI)

7. **Never commit proprietary PDKs, foundry data or NDA material.** That includes commercial PDK files, standard-cell libraries, `.lib`/`.lef`/`.gds` from licensed kits, DRC/LVS decks, and anything from an internship covered by an NDA. Use the open PDKs (SKY130, GF180MCU, IHP SG13G2) for public work.
8. **Never commit licensed EDA tool files.** No tool installers, license files, license-server addresses, or vendor-encrypted IP. Scripts for Cadence, Synopsys or Siemens tools are fine only if they contain no proprietary content.
9. **Respect academic integrity.** Don't publish solutions to *currently running* IIIT Dharwad assignments, labs or exams. Course-inspired projects are welcome after the course ends, or with the instructor's OK.
10. **Credit and license everything.** If you reuse code, a diagram or a design, keep its license and credit the author. Every repo must have a `LICENSE` (see [Repository Standards](docs/REPO_STANDARDS.md)).
11. **Use AI tools responsibly.** You may use AI assistants, but you must understand and be able to explain every line you submit. Mention significant AI help in your PR description. Don't submit unreviewed generated code.

## 🔐 Security and privacy

12. **No secrets in Git.** API keys, tokens, passwords and `.env` files never get committed. If one leaks, follow the [Security Policy](SECURITY.md) **immediately**; deleting the commit is not enough.
13. **Protect personal data.** Don't post phone numbers, roll numbers, marks or photos of people without their consent.
14. **Turn on two-factor authentication** on your GitHub account. It is required for org membership.

## 🛠️ Working on code and designs

15. **No direct pushes to `main`.** All changes go through a pull request. Ask for a review before merging anything non-trivial (see [CONTRIBUTING.md](CONTRIBUTING.md)).
16. **One PR = one change.** Keep pull requests focused and small enough to review in about 15 minutes.
17. **CI must pass.** Don't merge red builds. Don't disable checks to get green.
18. **Claim before you code.** Comment on an issue to have it assigned before you start, so two people don't do the same work. Unanswered claims expire after **7 days** of silence.
19. **Don't commit generated output.** Waveforms (`.vcd`, `.fst`), build directories, LibreLane/OpenLane `runs/` and simulator binaries belong in `.gitignore`. Final GDS/LEF for a tapeout goes in a release or a clearly marked folder.
20. **Document as you go.** A design without a README, block diagram and test instructions isn't finished.

## 🏛️ Org and repositories

21. **New repositories need a proposal.** Open a *Project Proposal* discussion first. The Core Team creates the repo from [`rtl-project-template`](https://github.com/GND-0/rtl-project-template) and names it per the [Repository Standards](docs/REPO_STANDARDS.md).
22. **Personal experiments go in your own account.** The org is for club projects with at least one maintainer and a clear goal. You can transfer a project in later.
23. **Inactive repos get archived.** No activity for **6 months** and no maintainer response means the repo is archived (not deleted). It can be revived any time.
24. **Speak for the club only when authorised.** Only the Core Team posts on the club's LinkedIn and Instagram or speaks to sponsors and companies on the club's behalf.

---

*Rules change through the [decision process](GOVERNANCE.md#how-decisions-are-made). Propose edits as a pull request to this file.*
