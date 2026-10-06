# AGENTS.md — far-engineering (the invention record)

> A patent is a document, and a document without a date is not one.

This file is the contract. Every filing record passes through it.

## What this repo is

A free, open-source **engineering school** for humans and for AI: the
invention record — patents, prior art, derivations, and the tools that
keep them honest.

**Purpose: patents, and the math underneath them.** The school teaches
by building. Every invention entry carries a test case, and every
derivation carries the invariant that makes it work across domains —
the same habit that turns an apparently unrelated set of geometries
into one falsifiable engineering statement.

It is not a university in the accreditation sense: no credits, no
tuition, no enrollment office. The output is a substrate that AI agents
and the humans working with them can use directly.

## What this repo is NOT

- **Not a university.** No credits, no tuition, no accreditation. A
  school without a price.
- **Not a patent office.** It files nothing. Not legal advice — use a
  registered patent attorney.
- **Not a claim repository.** An invention note is a *record of what was
  built and when*, not a legal assertion of novelty.

## The load-bearing distinction

Most patent material is **NOT free to redistribute**:

| Material | Status | Verdict |
|---|---|---|
| USPTO granted patents and published applications | US government works | **SAFE** — public domain |
| USPTO assignment and search APIs | public | **SAFE** |
| Prior-art cited by those patents (older patents, papers) | varies | verify per item |
| Our own engineering derivations and notes | ours | **MIT** |
| Commercial patent databases (LexisNexis, Derwent) | subscription | **NOT SAFE** |
| Google Patents page rendering | Google's compilation | do not bulk-copy |
| Scientific papers | mostly publisher-copyrighted | verify per item |
| WIPO / PCT documents | varies by office | verify per item |

**Rule: the patent text is public domain. Someone else's analysis of it
usually is not.** We index and cite; we do not scrape commercial
compilations.

## Divisions

Engineering disciplines, organized so an agent can navigate by field:

```
disciplines/
├── mechanical        # mechanisms, linkages, materials
├── electrical        # circuits, signals, power
├── civil             # structures, geotechnics
├── chemical          # process, materials synthesis
├── biomedical        # devices, bioengineering
├── thermal           # heat transfer, thermodynamics
├── optical           # photonics, imaging
├── acoustic          # sound, vibration, resonance
├── control           # feedback, autonomy
├── computing         # architectures, algorithms, hardware
├── manufacturing     # fabrication, tolerances, QC
└── fieldcore-link    # the geometric substrate these derive from
```

## Packet

```
Invention   invention_id | title | date_conceived | date_built | status
Filing      filing_id    | invention_id | office | number | date | url
Derivation  derivation_id| invention_id | source | target | invariant | test
PriorArt    prior_art_id | invention_id | citation | relation | url
```

## Axes

| Axis | Type | Values |
|---|---|---|
| `status` | enum | conceived, prototyped, built, tested, filed, granted, abandoned |
| `discipline` | enum | one of the directories above |
| `office` | enum | uspto, epo, wipo, ukipo, jpo, other |
| `date_conceived` | ISO-8601 | when it was first had |
| `date_built` | ISO-8601 | when it actually ran |
| `source_license` | enum | public-domain, cc-by, cc-by-sa, cc-by-nc-sa, ours, other |

## Dates are the substance

An invention record whose only date is the filing date is nearly
worthless — by then the clock on novelty has already run. We record
**conceived** and **built** separately, which is also what makes the
record useful to an agent deciding what is worth pursuing.

## The gate

The gate checks:

1. `title` non-empty
2. `status` on the list
3. `discipline` is a real directory
4. `date_conceived` and `date_built` parse as ISO-8601
5. `date_built` >= `date_conceived` — you cannot build before you conceive
6. a filing record carries `office` and a URL

## Anti-patterns

- filing dates presented as conception dates
- novelty asserted without prior art
- scraped commercial patent database text
- "revolutionary" with no test case
- a device with no dimensions, tolerances, or bill of materials

## Related

- the-far-queen/far-law/ — sibling repo, same gate shape
- the-far-queen/far-medicine/ — biomedical devices
- the-far-queen/far-mysteries/ — sacred library
- the-far-queen/fieldcore/ — the geometric substrate
- the-far-queen/simself/ — identity + constitutional kernel

## License

MIT for our own material. Third-party material retains its own license,
recorded per entry. Patent text is US public domain; everything else
must be checked.
