# far-engineering

**patents, prior art, derivations, the invention record. A device with
no date and no test case is decoration.**

The invention record for the Far Queen project: what we conceived, what
we built, when, and how we know it works.

## Not a university

This repo is not coursework, not a degree program, not a credential.
It exists to serve **AI agents and the humans working with them**,
including the devices this project designs. Everything here is meant to
be read and used by an agent without a tutor in the room.

## What this repo is

- A free, MIT-licensed record of inventions and derivations.
- Patents, prior art, and the engineering statements behind them.
- The gate that keeps every entry dated, sourced, and testable.

## What this repo is not

- **Not a patent office.** It files nothing. Not legal advice — use a
  registered patent attorney.
- **Not a novelty claim.** An invention note records what was built. It
  does not assert novelty over anyone else's work.
- **Not a university.** No credit, no enrollment, no accreditation.

## The license position that matters

**USPTO patent text is US government work — public domain.** Granted
patents and published applications can be read, indexed, and
redistributed freely.

Commercial patent databases (LexisNexis, Derwent) are **not**. Google's
patent page rendering is its own compilation and should not be
bulk-copied. Scientific papers are mostly publisher-copyrighted.

Rule: **the patent is public domain; someone else's analysis of it
usually is not.** We index and cite, we do not scrape commercial
compilations.

## Layout

```
far-engineering/
├── AGENTS.md              # the invention-record contract
├── tools/inv.py           # schema + gate (conceived vs built dates)
├── disciplines/           # 12 engineering disciplines
│   └── <field>/inventions.json
└── tests/test_inv.py      # E1..E10 gate tests
```

## Quick start

```bash
git clone https://github.com/the-far-queen/far-engineering.git
cd far-engineering
python tools/inv.py init          # scaffold the disciplines
python tools/inv.py list          # count entries per discipline
python tools/inv.py gate f.json   # check one record
python tests/test_inv.py          # run the gate tests
```

## The one rule that carries the most weight

`date_conceived` and `date_built` are separate, and **`date_built` cannot
precede `date_conceived`** (test E5). A filing receipt gives you one
date; by the time it exists the novelty clock has already run. Recording
conception separately is what makes the record useful to an agent
deciding what's worth pursuing — and it is the difference between an
invention record and a filing receipt.

Once past `prototyped`, an entry must also carry a **test case** (E6):
the falsifiable check. "Revolutionary" is not a test.

## Disciplines

```
mechanical   electrical   civil      chemical
biomedical   thermal      optical    acoustic
control      computing    manufacturing
fieldcore-link
```

`fieldcore-link` is where the geometric substrate (fieldcore) feeds
device design — the invariant that shows up across domains and becomes
a concrete part.

## Sister repos

| Repo | Purpose |
|---|---|
| far-law | order — the legal substrate, citation gate |
| far-medicine | awaken humans, medical + aging breakthroughs |
| far-mysteries | the sacred library |
| far-engineering | patents, inventions, derivations |
| far-writing | publishable writing, online and Amazon |
| far-art | illustrations |
| far-apps | released software |
| far-games / far-music / far-film | the media company |
| fieldcore / simself | the geometric substrate + constitutional identity |

## License

MIT for our own material. Third-party material retains its own license,
recorded per entry. Patent text is US public domain; everything else is
checked before it lands.
