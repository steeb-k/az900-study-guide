# Microsoft Azure Fundamentals AZ-900 Study Kit

> **⚠ AI-generated, not yet vetted.** Every file in this repository (study guide chapters, reference sheets, and the companion
> question bank) was written by AI against Microsoft's AZ-900 skills outline and has **not yet been reviewed by a human for
> accuracy**. Azure also changes often. Treat it as a study aid, not an authoritative source: cross-check anything surprising
> against [Microsoft Learn](https://learn.microsoft.com/en-us/credentials/certifications/azure-fundamentals/) before relying on it.

**Read it online:** [steeb-k.github.io/azure/az-900/guide/](https://steeb-k.github.io/azure/az-900/guide/) (sidebar navigation, acronym tooltips, search) · practice exams at [steeb-k.github.io/azure/az-900/](https://steeb-k.github.io/azure/az-900/).

A compact, exam-focused study kit for **AZ-900: Microsoft Azure Fundamentals**, following the skills measured as of **July 20, 2026**. It assumes you already work in IT: each file follows Microsoft's skill groups, defines every bullet the way the exam tests it, and flags commonly confused pairs. No fluff.

Microsoft does not number its skill groups. The `1.1` … `3.4` numbers used throughout are this kit's own, so the guide and the practice questions can point at each other.

## File index

Want it all in one place? **[STUDY-GUIDE-FULL.md](STUDY-GUIDE-FULL.md)** is every chapter and reference sheet in a single file (regenerate with `python3 meta/build-full.py`).

| File | Contents |
|---|---|
| `00-exam-overview.md` | Exam facts, domain weights, question types, scoring, time management, logistics, 1- and 2-week schedules |
| `01-cloud-concepts.md` | Domain 1 (25–30%): cloud computing, shared responsibility, cloud models, pricing, benefits, IaaS/PaaS/SaaS |
| `02-azure-architecture-services.md` | Domain 2 (35–40%): regions and zones, resource hierarchy, compute, networking, storage, identity and security |
| `03-azure-management-governance.md` | Domain 3 (30–35%): cost management, Purview, Policy, locks, management and deployment tools, monitoring |
| `90-service-picker.md` | "The requirement says X, the answer is Y" tables, plus services that sound alike and are not |
| `91-acronyms.md` | AZ-900 acronym list with one-line meanings |
| `92-numbers-and-comparisons.md` | The countable facts and side-by-side tables: redundancy, tiers, hierarchy limits, roles, locks |

## Companion practice site

**[steeb-k.github.io/azure/az-900](https://steeb-k.github.io/azure/az-900/)**

- Per-domain module quizzes in **practice mode** (instant feedback and explanation) or **exam mode** (feedback at the end)
- **Interactive items** in the style of the real exam: yes/no statement grids, matching, ordering, dropdown tables
- **Missed-question drill**: re-quizzes only the questions you have gotten wrong
- **Full 40-question timed final** (45:00 clock, 4 interactive items first, then 36 domain-weighted questions)
- **Score history**: percent, estimated scaled score (pass line 700), per-domain breakdown

The questions are original. They imitate the style of Microsoft's exam; none are copied from Microsoft's practice assessment or
from any exam. Use Microsoft's free [practice assessment](https://learn.microsoft.com/en-us/credentials/certifications/azure-fundamentals/practice/assessment?assessment-type=practice&assessmentId=23) and [exam sandbox](https://aka.ms/examdemo) as well.

## HTML version

The same chapters are published as a searchable web guide at **[steeb-k.github.io/azure/az-900/guide/](https://steeb-k.github.io/azure/az-900/guide/)**: sidebar navigation, full-text search, acronym tooltips, highlights, and deep links from the practice quiz's objective lines. The Markdown files stay the only source; the site data is generated from them. After editing any chapter:

```
python3 meta/build-full.py     # STUDY-GUIDE-FULL.md
python3 meta/build-site.py     # ../steeb-k.github.io/azure/az-900/guide/data/guide.js and ../data/acronyms.js
cd ../steeb-k.github.io/azure/az-900 && bash tests/guide-sync.sh && bash tests/smoke.sh guide/index.html
```

## Suggested study loop

1. Read a domain file (start with `00-exam-overview.md`).
2. Take that domain's module quiz (practice mode first, exam mode once comfortable). Repeat until **3 consecutive attempts at 80% or higher**.
3. Move to the next domain.
4. Run the **missed-question drill** after each domain and again before final exams.
5. Review `90-`, `91-`, and `92-` the day before the exam.
6. Take full final exams until you are **consistently at or above 800 estimated** (the pass line is 700; leave a margin).

## Version note

Microsoft revises the AZ-900 skills outline a few times a year, usually with minor changes. This kit targets the outline dated
**July 20, 2026**; check the [official study guide](https://aka.ms/AZ900-StudyGuide) for a newer date before your exam.

## About this repo

The content was AI-generated (drafted, then independently reviewed by a second pass) and is maintained alongside the companion
practice site ([source](https://github.com/steeb-k/steeb-k.github.io/tree/main/azure/az-900)). Specs (overview, question schema,
visual design, guide site) are in [`meta/`](meta/). Corrections are welcome via issues or pull requests.

Not affiliated with or endorsed by Microsoft. Azure and Microsoft are trademarks of the Microsoft group of companies.
