# Computer Science Vault

---

## Progress Overview

```dataview
TABLE length(rows) AS "Total"
FROM "03 Knowledge"
GROUP BY status
```

## Currently In Progress

```dataview
TABLE file.folder AS "Phase"
FROM "03 Knowledge"
WHERE status = "In Progress"
SORT file.mtime DESC
```

## Recently Updated

```dataview
TABLE status
FROM "03 Knowledge"
SORT file.mtime DESC
LIMIT 10
```

## Needs Review

```dataview
LIST
FROM "03 Knowledge"
WHERE status = "Needs Review"
```

---

## Quick Links

- [[01 Roadmaps/Phase 01 — Foundation]]
- [[01 Roadmaps/Phase 02 — Programming Fundamentals]]
- [[01 Roadmaps/Phase 03 — Data Structures]]
- [[01 Roadmaps/Phase 04 — Algorithms]]

---

## Milestones

- [ ] Milestone 1 — Functional Vault (50 notes)
- [ ] Milestone 2 — Core CS (200 notes)
- [ ] Milestone 3 — Systems (400 notes)
- [ ] Milestone 4 — Full Curriculum (700 notes)
- [ ] Milestone 5 — Practice and Projects (1,000 notes)
