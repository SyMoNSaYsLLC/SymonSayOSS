# SymonSayOSS

Open source code: permissively licensed work, kept apart from the proprietary distribution
and from the copyleft builds.

## The four trees, and what decides which one something is in

| Repository | Holds | Licence |
|---|---|---|
| `SymonSayDistribute` | the runtimes we sell, one branch each, each cutting its own releases | FSL-1.1-ALv2, source-available, no copyleft |
| `SymonSayOSS` | code we publish openly | permissive: MIT, BSD, Apache-2.0 |
| `SymonSayOpen` | builds whose output is copyleft, laid out like the distribution | MIT metadata; outputs stay copyleft |
| `SymonSaySource` | what we build from: pins, licences, provenance — never the source bytes | tracking only; ships nothing |

The question that places something is **what licence does the thing we ship under, and can it
be linked into a product release**:

- shipped as product, no copyleft → `SymonSayDistribute`
- published openly and permissively, anyone may take it → `SymonSayOSS`
- its output is copyleft, so it may never link into a product release → `SymonSayOpen`
- it is somebody else's source we build from → `SymonSaySource`

**Anything that fits none of these is a conversation, not a guess.** It is recorded and raised,
and work continues around it rather than stopping on it.

## Why open source at all, when the product is not

Two different jobs. The runtimes are the product and are licensed to become Apache-2.0 two
years after each release, which is a commercial decision about a commercial thing. Some of
what we build is not the product: a licence gate, a reproducible wheel builder, a tool that
lays a repository out on disk. Those are useful to anyone and cost nothing to give away, and
holding them under a proprietary licence buys nothing while making them harder to reuse even
for us.

## How it is laid out

| Branch | Holds |
|---|---|
| `main` | this index, and nothing else |
| one per project | that project's source, its own documentation, its own history |

A project here cuts its own releases, the same way a runtime does in the distribution.

## Candidates, not yet moved

These are first-party, general-purpose, and would lose nothing by being open. Each is a
decision rather than an assumption, so they stay where they are until that decision is made:

| Candidate | What it is | Where it lives today |
|---|---|---|
| ship gate | classifies every component's licence and refuses a release on copyleft, secrets, weights, trademarks or known vulnerabilities | distribution `workflow` branch |
| wheel builder | a reproducible wheel for a pure-Python package, without a build backend | distribution `workflow` branch |
| release archiver | collapses a staged tree into one reproducible archive, keeping symbolic links | distribution `workflow` branch |
| disk layout | lays a repository out as one directory per branch | distribution `workflow` branch |
