# Governance

How GND_0 VLSI Club is organised, who decides what, and how responsibility is handed over each year.

Principles: **open by default, merit through contribution, continuity across batches.**

---

## Roles

| Role | Who | GitHub access | Responsibilities |
|---|---|---|---|
| **Learner** | Anyone, inside or outside IIIT Dharwad | None needed | Learn, ask, open issues, send PRs from forks |
| **Member** | IIIT Dharwad students who complete [onboarding](MEMBERSHIP.md) | Org member, **read** on all repos | Take part in projects, events and Discussions |
| **Contributor** | Members with at least 1 merged PR | Added to a domain team, **triage** | Triage issues, review PRs, help newcomers |
| **Maintainer** | Trusted contributors who own a repo | **Maintain** on their repo(s) | Review and merge PRs, plan releases, keep the repo healthy |
| **Domain Lead** | One per technical domain | **Maintain** on domain repos; maintainer of the domain team | Plan learning content and projects for the domain, mentor maintainers |
| **Core Team** | Elected office bearers | **Org owner** (max 3) or admin | Run the club, steward the org, final decisions |
| **Faculty Advisor** | IIIT Dharwad faculty member | Org owner (break-glass) | Guidance, institute liaison, conduct escalations |
| **Alumni Mentor** | Graduated members and industry friends | Member of `@GND-0/mentors` | Talks, reviews, career guidance |

### Core Team positions
| Position | Focus |
|---|---|
| **Club Lead** | Overall direction, institute relations, chairs Core meetings |
| **Co-Lead** | Operations, deputises for the Lead, owns this governance doc |
| **Technical Lead** | Technical roadmap across domains, repository standards, CI |
| **Events Lead** | Workshops, hackathons, talks, the semester calendar |
| **Outreach Lead** | Social media, website content, sponsor and industry contacts |
| **Community Lead** | Onboarding, Discussions moderation, Conduct Committee chair |

Positions can be merged or split depending on team size.

### Domain teams
Each domain has a GitHub team (`@GND-0/<team>`), a Domain Lead and its own learning track in the [Roadmap](learning/ROADMAP.md).

| Team | Scope |
|---|---|
| `@GND-0/digital-design` | RTL design, microarchitecture, RISC-V |
| `@GND-0/verification` | Testbenches, SystemVerilog/UVM, cocotb, formal |
| `@GND-0/physical-design` | Synthesis, STA, LibreLane/OpenROAD, tapeouts |
| `@GND-0/analog` | Analog/mixed-signal, custom layout, SPICE |
| `@GND-0/fpga` | FPGA prototyping and demos |
| `@GND-0/web` | Website, Sanity studio, tooling |
| `@GND-0/events` | Event planning and logistics |
| `@GND-0/mentors` | Alumni and industry mentors |
| `@GND-0/core` | Core Team |
| `@GND-0/maintainers` | All repo maintainers (umbrella team) |

### Current office bearers

> 🛠️ *Core Team: keep this table current. Update it in the same PR as every handover.*

| Role | Name | GitHub |
|---|---|---|
| Faculty Advisor | _TBD_ | _@handle_ |
| Club Lead | _TBD_ | _@handle_ |
| Co-Lead | _TBD_ | _@handle_ |
| Technical Lead | _TBD_ | _@handle_ |
| Events Lead | _TBD_ | _@handle_ |
| Outreach Lead | _TBD_ | _@handle_ |
| Community Lead | _TBD_ | _@handle_ |

Repository maintainers are listed in [docs/MAINTAINERS.md](docs/MAINTAINERS.md).

---

## How decisions are made

We use **lazy consensus** for most things and escalate only when needed.

| Decision type | Examples | Process |
|---|---|---|
| **Everyday** | Merging a PR, labelling, small doc fixes | Maintainer decides |
| **Repo-level** | New feature direction, breaking change, new maintainer for that repo | Issue or Discussion. If no objection from repo maintainers in **3 days**, it passes. |
| **Club-level** | New repo, new event series, rule changes, budget | **Proposal** in Discussions (category *Proposals*). Open for **7 days**, then a Core Team vote, simple majority. |
| **Governance** | Changing this file, roles or the Code of Conduct | Proposal open **14 days**, then Core Team **two-thirds** majority, plus no veto from the Faculty Advisor |
| **Emergency** | Leaked secret, abuse, compromised account | Any owner acts immediately and reports to the Core Team within 24 h |

**Proposal format:** title `[Proposal] …`, then *Problem → Proposal → Alternatives considered → Impact → Owner*. A template is provided in Discussions.

Ties are broken by the Club Lead. Core Team decisions and their reasoning are recorded in the Discussion thread so future batches understand *why*.

---

## Becoming a maintainer

A contributor can be nominated (self-nomination is fine) when they have, **for that repo**:

- [ ] at least **3 merged, non-trivial PRs**
- [ ] at least **3 helpful reviews** on others' PRs
- [ ] shown good judgement and followed the [Code of Conduct](CODE_OF_CONDUCT.md)

Process: open an issue in `GND-0/.github` titled `Maintainer nomination: @handle for <repo>`. Existing maintainers and the Domain Lead comment. If there's no objection in **7 days**, the Technical Lead grants access and adds the person to [MAINTAINERS.md](docs/MAINTAINERS.md).

**Stepping down / emeritus:** maintainers may step down any time. After **6 months** of inactivity, access is reduced to triage and the person is listed as *Emeritus*. They are welcome back at any time.

---

## Annual handover

Student communities fail when one batch leaves and takes the knowledge with it. To prevent this:

1. **Elections or selection** for the Core Team happen each year before the end of the even semester, as decided by the outgoing Core Team and Faculty Advisor. The method (election by members, or interviews) is announced in Discussions at least 2 weeks ahead.
2. **Shadow period:** incoming leads shadow outgoing leads for at least **4 weeks**.
3. **Handover checklist** (owned by the Co-Lead):
   - [ ] Update the office-bearers table and [MAINTAINERS.md](docs/MAINTAINERS.md)
   - [ ] Transfer org owner role; remove owner access from outgoing members (they stay in `@GND-0/mentors` if they want)
   - [ ] Rotate shared credentials: Sanity tokens, Firebase, Vercel, email app passwords, social accounts
   - [ ] Hand over the club email, domain and hosting accounts (Vercel, Sanity, Firebase) to institute-owned or club-owned accounts, never personal ones
   - [ ] Archive the year's events and reports in Discussions → Announcements
   - [ ] Write a "state of the club" retrospective as a Discussion
4. **Ownership safety:** the org must always have **at least 2 student owners plus the Faculty Advisor** as owners, so nobody gets locked out.

---

## Conduct Committee

Three people: the **Community Lead** (chair), one other Core Team member, and one Maintainer or Faculty Advisor. They handle [Code of Conduct](CODE_OF_CONDUCT.md) reports. A member involved in a report must step aside from handling it.

## Changes to this document

Use the **Governance** process above. Open a PR against this file and link the Proposal discussion.
