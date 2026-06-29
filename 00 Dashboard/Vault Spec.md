# Computer Science Vault — Project Specification

> Version: 2.0
> Status: Active
> Purpose: Single source of truth for the vault's architecture, conventions, and design decisions.

---

## Project Goal

Build a complete, long-term Computer Science knowledge base in Obsidian using Coding Interview
University as the curriculum backbone.

The goal is not interview preparation. The goal is deep, lasting Computer Science knowledge
that grows with you for years.

---

## Philosophy

The vault should feel like official documentation — clean, structured, authoritative.

It should not feel like a productivity app, a checklist, or a random collection of notes.

---

## Design Principles

**Simplicity.** Clean Markdown. No visual clutter. No excessive formatting.

**Consistency.** Every note type follows the same structure. Consistency matters more than novelty.

**One concept, one note.** Every concept gets its own file. Nothing shares a note unless
it is genuinely inseparable.

**Small notes.** A note should take a few minutes to read. If it grows too long, split it.

**Meaningful links.** Only link notes when a real relationship exists. Do not link for the
sake of the graph.

**Graph-first.** The Obsidian graph should naturally show prerequisite clusters without
manual arrangement.

---

## Folder Structure

```
00 Dashboard/
01 Roadmaps/
02 Maps/
03 Knowledge/
    01 Foundation/
    02 Programming Fundamentals/
    03 Data Structures/
    04 Algorithms/
    05 Mathematics/
    06 Computer Architecture/
    07 Operating Systems/
    08 Networking/
    09 Databases/
    10 System Design/
    11 Programming Languages/
    12 Linux and Git/
    13 Security/
04 Practice/
05 Projects/
06 Resources/
07 Reviews/
08 Templates/
```

---

## Numbering Convention

Files use a two-digit prefix within their folder. The folder provides the topic context.
The number preserves reading order.

```
01 Arrays.md
02 Linked Lists.md
03 Stacks.md
04 Queues.md
```

If a new note needs to go between existing ones, use a letter suffix rather than renumbering
everything:

```
02 Linked Lists.md
02b Doubly Linked Lists.md
03 Stacks.md
```

Inside every note, the heading is the concept name only — no number:

```markdown
# Arrays
```

---

## Four-Layer Architecture

### Layer 1 — Roadmaps

**Purpose:** Define what to learn and in what order.
**Contains:** Ordered topic list, progress checkboxes, links to Maps.
**Does not contain:** Explanations, definitions, or any learning content.

One roadmap file per phase. Each roadmap is short and clean.

---

### Layer 2 — Maps

**Purpose:** Navigate a topic cluster. Acts as the entry point into any major subject.
**Contains:** Brief one-line description of each concept, links to Knowledge notes,
a live Dataview query showing completion status.
**Does not contain:** Deep explanations.

One Map per major topic. The Map for Data Structures links to every data structure note
and shows how many are complete. Implemented using Folder Notes — each Knowledge subfolder
has an attached Map note.

---

### Layer 3 — Knowledge

**Purpose:** Learn a concept.
**Contains:** Definition, explanation, examples, diagrams, connections to related notes.
**Does not contain:** Practice problems or exercises. The Practice section is a link only.

---

### Layer 4 — Practice

**Purpose:** Apply knowledge.
**Contains:** Problems, exercises, worked solutions, mistakes, observations.
**Does not contain:** Learning content of any kind.

---

## Note Templates

Two templates. Choose based on the complexity of the concept.

---

### Lite Template

Use for simple, atomic concepts.

Examples: Variable, Data Type, Pointer, Boolean, Stack, ASCII.

```markdown
---
title:
status: Draft
tags: []
created: {{date:YYYY-MM-DD}}
---

# {{title}}

## Overview

## Key Points

## Example

## Related Concepts

## Resources
```

---

### Full Template

Use for complex, multi-part concepts.

Examples: Binary Search Tree, Dynamic Programming, TCP/IP, Virtual Memory, Hash Table.

```markdown
---
title:
status: Draft
tags: []
created: {{date:YYYY-MM-DD}}
---

# {{title}}

## Overview

## Why It Matters

## Core Concepts

## Examples

## Key Takeaways

## Common Mistakes

## Related Concepts

## Practice
<!-- Link only: [[04 Practice/Topic/Note]] -->

## Resources
```

---

### Choosing a Template

Use Lite if the concept can be fully explained in under ten sentences.

Use Full if the concept has multiple sub-components, its own algorithms, or significant
real-world application.

The Practice section in the Full template is always a link. Never write exercises or
problems inside a knowledge note.

---

## Status Values

Every note has a `status` field in its frontmatter. Only these four values are valid:

| Value | Meaning |
|---|---|
| `Draft` | Created, minimal or no content yet |
| `In Progress` | Being actively written |
| `Complete` | Content is finished and reviewed |
| `Needs Review` | Flagged for correction or expansion |

---

## Tag Taxonomy

Tags handle cross-cutting concerns that folders cannot. Use only the tags defined below.
Do not invent new tags without updating this section of the spec.

**Topic tags**
```
#topic/foundation
#topic/programming
#topic/data-structures
#topic/algorithms
#topic/mathematics
#topic/architecture
#topic/os
#topic/networking
#topic/databases
#topic/system-design
#topic/languages
#topic/linux
#topic/security
```

**Type tags**
```
#type/concept
#type/algorithm
#type/data-structure
#type/pattern
#type/theorem
```

**Complexity tags** — for algorithm and data structure notes only
```
#complexity/O1
#complexity/Ologn
#complexity/On
#complexity/Onlogn
#complexity/On2
#complexity/exponential
```

**Flashcard tag** — marks a line or block for Spaced Repetition review
```
#flashcard
```

---

## Resources

Resource notes live exclusively in `06 Resources/`. They are never mixed into
Knowledge notes.

Each knowledge note links to at most one or two resource notes in its Resources section.
The actual content — links, descriptions, ratings — stays in `06 Resources/`.

---

## Progress Tracking

Progress is tracked automatically using Dataview queries in the Dashboard and Map notes.
No manual percentage tracking. The Dashboard always reflects the real state of the vault.

Example query — notes by status across all Knowledge:

```dataview
TABLE status, tags
FROM "03 Knowledge"
GROUP BY status
```

Example query — incomplete notes in Data Structures:

```dataview
TABLE status
FROM "03 Knowledge/03 Data Structures"
WHERE status != "Complete"
SORT file.name ASC
```

---

## Plugins — How Each Is Used

**Templater**
Creates notes with the correct template pre-filled. Trigger on new file creation is enabled.
Template folder is set to `08 Templates/`.

**Dataview**
Powers the Dashboard and all Map notes. Queries frontmatter for live progress.
JavaScript queries are enabled.

**Git**
Auto-commits and pushes to GitHub every 30 minutes. Already configured and connected
to NyxaIith/CIU-study-tracker.

**Spaced Repetition**
Flashcard review built into Obsidian. Key definitions in knowledge notes are marked
with `#flashcard` for scheduled review. No separate app needed.

**Excalidraw**
Embedded diagrams for data structures, algorithm flows, memory layouts, and system designs.
Diagrams live inside the relevant knowledge note or its folder.

**Linter**
Enforces consistent formatting automatically on save. Keeps frontmatter clean and
spacing uniform across all notes.

**Folder Notes**
Each Knowledge subfolder has an attached Map note. Clicking the folder opens the Map,
not a file list.

**Tag Wrangler**
Manages tags globally. Always use Tag Wrangler to rename or merge tags.
Never rename tags manually across individual files.

**Advanced Tables**
Used in roadmap notes and any comparison or summary notes.

**Iconize**
Visual icons on folders for faster navigation.

**Kanban**
Tracks current study status across phases: To Learn — Learning — Complete.

**Calendar**
Shows which days had active study sessions.

**Checklist**
Aggregates all incomplete tasks and exercises from across the vault into one view.

**Reading Time**
Signals when a note is getting too long and may need splitting.

**Minimal Theme + Minimal Theme Settings**
Base visual theme. Produces a clean, documentation-like appearance.

---

## Roadmap

Fifteen phases. Docker and Kubernetes are not included — they are DevOps tools, not
Computer Science, and belong in a separate vault if needed later.

```
Phase 01 — Foundation
Phase 02 — Programming Fundamentals
Phase 03 — Data Structures
Phase 04 — Algorithms
Phase 05 — Mathematics for CS
Phase 06 — Computer Architecture
Phase 07 — Operating Systems
Phase 08 — Networking
Phase 09 — Databases
Phase 10 — System Design
Phase 11 — Programming Languages
Phase 12 — Linux and Git
Phase 13 — Security
Phase 14 — Practice
Phase 15 — Projects
```

---

## Milestones

The long-term vision of 2,500–3,000 notes is preserved. These intermediate checkpoints
make the journey measurable.

**Milestone 1 — Functional Vault (50 notes)**
Vault structure complete. All templates working. Git confirmed. Foundation phase done.
Dashboard live with Dataview queries.

**Milestone 2 — Core CS (200 notes)**
Data Structures, Algorithms, and Mathematics phases complete.

**Milestone 3 — Systems (400 notes)**
Computer Architecture, Operating Systems, Networking, and Databases phases complete.

**Milestone 4 — Full Curriculum (700 notes)**
System Design, Programming Languages, Linux and Git, Security phases complete.

**Milestone 5 — Practice and Projects (1,000 notes)**
Practice and Projects phases complete. Vault is fully functional as a study tool.

**Long-term vision (2,500–3,000 notes)**
Ongoing expansion beyond CIU using MIT, Berkeley, OSTEP, DDIA, and other
respected sources listed in the Expansion Policy.

---

## Expansion Policy

Expansion beyond Coding Interview University is allowed only with widely respected sources:

- CS50 — Harvard
- MIT OpenCourseWare
- UC Berkeley courses
- OSTEP — Operating Systems: Three Easy Pieces
- Beej's Guide to Network Programming
- CMU Database course
- The System Design Primer
- Designing Data-Intensive Applications
- Official language and tool documentation

---

## Quality Standard

Every note must be:

- **Clear** — Understandable without needing other notes for basic context
- **Concise** — No filler, no padding, no repetition
- **Correct** — Verified against at least one trusted source
- **Connected** — Linked to related notes, tagged correctly
- **Expandable** — Structured so adding content later is straightforward

If a note feels cluttered, simplify it.
If reading it takes more than ten minutes, split it.

---

## Style Guide

- Simple Markdown only
- No excessive bold or italic
- No decorative emojis in knowledge notes
- Short paragraphs — two to four sentences maximum per paragraph
- Code blocks for all code, even single lines
- Excalidraw for all diagrams — no ASCII art

---

## Changelog

| Version | Change |
|---|---|
| v1.0 | Initial spec written |
| v2.0 | Simplified numbering system. Two-tier template system. Status values defined. Tag taxonomy added. Four-layer architecture with Maps. Practice contradiction resolved. Docker and Kubernetes removed. Plugin usage documented. Intermediate milestones added. Real World Examples placeholder removed. |
