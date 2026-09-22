# PURSUE UAP media records — a DVIDS-verified index

An open dataset of the video and audio files released by the U.S. Department of War
under the **Presidential Unsealing and Reporting System for UAP Encounters (PURSUE)**,
each one reconciled against its own record on
[DVIDS](https://www.dvidshub.net/), the Department of Defense's media distribution service.

**86 media records. 82 verified individually against DVIDS. 3 partial. 1 unverified and
flagged as such.**

Maintained alongside [uapdisclosure.live](https://uapdisclosure.live/).

---

## Why this exists

Most published accounts of the PURSUE releases summarise press coverage. This dataset
records what the government itself published: every entry carries AARO's own description
of the file, taken from the DVIDS record, not a journalist's paraphrase of it.

Where something could not be confirmed, it says so rather than filling the gap.

## Files

| File | Contents |
|---|---|
| `pursue-media-records.csv` | 86 media records, one row each |
| `pursue-media-records.json` | The same data as JSON |
| `pursue-timeline.csv` | 21 disclosure events — releases, reports, hearings, policy actions |

## Fields

| Field | Meaning |
|---|---|
| `reference_id` | The Department's own identifier, e.g. `DOW-UAP-PR135`, `LLE-UAP-PR001`, `NASA-UAP-D026` |
| `tranche` | `R01`–`R06` |
| `tranche_label` | Release number and publication date |
| `title` | Title exactly as published on DVIDS |
| `date_taken` | Year or date of the recording, as stated |
| `location` | As stated on the record; often "undisclosed" |
| `submitting_command` | e.g. U.S. Central Command, U.S. Indo-Pacific Command |
| `duration` | Runtime |
| `verification` | `verified` · `partial` · `unverified` — see below |
| `aaro_description` | Condensed from AARO's published description |
| `source_url` | Link to the DVIDS record |

## What the verification levels mean

- **`verified`** — the DVIDS record was retrieved and read directly. Title, date, duration,
  command and description all come from that page.
- **`partial`** — sourced from search results or reporting; not confirmed against the
  record itself.
- **`unverified`** — could not be reconciled with any DVIDS record. One entry, a
  "2025 Middle East Populated-Area Clip", carries this. Every Release 05 Middle East 2025
  clip was checked and none matches. It may be a duplicate, or the detail may have come
  from a faulty search snippet. It is kept, flagged, rather than quietly removed.

## Coverage, stated honestly

| Tranche | Records here | Reported total |
|---|---|---|
| R01 | 6 | ~29 videos |
| R02 | 28 | ~51 videos |
| R03 | 0 | mostly documents |
| R04 | 22 | PR100–PR116, sequence complete |
| R05 | 14 | 16 videos |
| R06 | 16 | 15 videos + 1 audio, complete |

R01, R02 and R03 are incomplete. That is a gap in this dataset, not evidence about what
was released.

## Two findings worth knowing if you are building your own index

**1. Reference numbers do not run in order by tranche.** `DOW-UAP-PR024` and
`DOW-UAP-PR030` both publish on 10 July 2026 and belong to Release 04, despite sitting
numerically among Release 01 material. Sorting by reference number will mis-file records.

**2. Files are staged on DVIDS before the announcement.** Publication timestamps:

```
Release 01, announced 8 May    → PR21 19:48, PR22 23:22, PR23 23:30 on 7 May
Release 03, announced 12 June  → D023 08:36 on 11 June; D024 07:00 on 12 June
Release 06, announced 18 Sept  → PR148 07:15 on 18 Sept
```

Items appear the evening before the announcement or the morning of it. A record
timestamped the night before belongs to that release. Treating publication date as a
strict tranche boundary excludes real items — this dataset initially made that mistake.

## A note on file counts

The Department's own announcements give **no file counts and no item descriptions**.
Figures such as "71 files in Release 06" come from independent reviews by news outlets,
not from the Department. This dataset therefore counts only what it can point at: the
individual DVIDS records.

## Licence and provenance

The underlying records are U.S. Government works, published on DVIDS and war.gov, and are
in the public domain. This compilation — the reconciliation, the verification flags and
the structure — is offered freely. Use it, correct it, fork it.

Corrections are welcome and wanted. If a record here disagrees with the DVIDS page, the
DVIDS page is right.
