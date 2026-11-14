# Events Playbook

Recurring formats that keep the community active, and a checklist so any batch can run them.

## Recurring formats

| Format | Cadence | What happens | Owner |
|---|---|---|---|
| ⏚ **GND Hours** | Weekly, 1–1.5 h | Open lab and study circle following the [Roadmap](../learning/ROADMAP.md). Seniors help juniors debug. | Domain Leads (rotating) |
| 🧪 **HDLBits Sprint** | First 6 weeks of odd semester | Leaderboard challenge for new members; top finishers get a mention on the website | Digital design lead |
| 🔍 **Review Club** | Fortnightly | Live code review of a member's PR or an open-source core (Ibex, PicoRV32...) | Technical Lead |
| 📰 **VLSI Pulse** | Monthly | Industry news and paper digest published on the website (`vlsiPulse` page) | Outreach Lead |
| 🎤 **Industry / Alumni Talk** | 1–2 per semester | Engineers on real-world flows and careers; record if allowed | Events Lead |
| 🏁 **Design Hackathon** | Once a year | 24–48 h RTL / FPGA / verification challenges, judged on working demos | Events Lead |
| 🧩 **Tapeout Cohort** | Aligned to a Tiny Tapeout shuttle | Teams of 2–4 take a design from spec to submitted GDS over ~10 weeks | Physical-design lead |
| 🎓 **Demo Day** | End of each semester | Every project demos; badges awarded; recordings posted | Core Team |
| 🤝 **Mock Interviews** | Before placement and internship season | Alumni mentors run technical mocks | Community Lead |

## Tapeout Cohort plan (~10 weeks)

| Week | Milestone | Done when |
|---|---|---|
| 1 | Teams formed, idea pitched | Project Proposal discussion approved |
| 2 | Spec and block diagram | `docs/spec.md` merged |
| 3–5 | RTL and unit tests | CI green, coverage of the main features |
| 6 | Integration with the shuttle's template (pins, clock, reset) | Template test-bench passes |
| 7–8 | Hardening | GDS generated, timing met, precheck clean |
| 9 | Documentation and review | Datasheet/README complete, peer review done |
| 10 | **Submit** before the shuttle deadline | Submission confirmed |

Budget: check current per-tile pricing on [tinytapeout.com](https://tinytapeout.com/). Seek sponsorship from the institute, alumni or industry early. Shuttle schedules change, so lock dates against the [runs page](https://tinytapeout.com/runs).

## Event checklist

**4+ weeks before**
- [ ] 🎤 *Event / workshop* issue opened in `GND-0/.github` with an owner
- [ ] Venue / lab booked; institute permissions if needed
- [ ] Speaker confirmed (send them the Code of Conduct)
- [ ] Budget approved by the Core Team

**2 weeks before**
- [ ] Announcement in Discussions → Announcements, plus LinkedIn and Instagram
- [ ] Pre-install instructions published (tool versions, WSL2 for Windows)
- [ ] Material in a repo (`event-<name>-<year>`) or folder; tested on a clean machine

**On the day**
- [ ] Attendance (no phone numbers collected in public sheets)
- [ ] Photos with consent; a volunteer for Q&A in Discussions

**Within 1 week after**
- [ ] Slides, code and recording links posted in the event's Discussion
- [ ] Short report (attendance, what went well, what to change) added to the issue, then close it
- [ ] Website updated via the Sanity studio (events, gallery)
