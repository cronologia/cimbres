# Context — cronologia/cimbres

## What this repo is

A source-referenced chronology of the Marian apparitions **reported in 1936** at
Sítio Guarda, near the village of Cimbres, municipality of Pesqueira,
Pernambuco, Brazil — attributed by the devotion to Nossa Senhora das Graças —
together with the Church's response and the shrine that grew at the site.

It is one of a family of Cronologia projects; it follows the shared sourcing
discipline in `.claude/skills/sourcing-rules/SKILL.md`. The apparitions are
recorded as **reported events**. The dataset documents who reported what and
when, and what Church authorities ruled and when, citing the ruling document.
It never asserts the supernatural claim as fact.

## Current state (2026-08-05, bootstrap)

- 13 events, 6 figures, 13 references, plus facts, organizations and a
  disambiguation block.
- Three locales (en / es / pt) built from `data/chronology.json`; the es and pt
  dictionaries are exact-key, hand-authored by the assistant and **not**
  human-reviewed (`_meta.humanReviewed: false`, and the page banner says so).
- Gate green: `validate-data.js`, `node --test` (144), `build.js`.

## The central finding

**No formal diocesan ruling from the 1930s–40s has been located.** A 2023
academic study concludes the devotion consolidated "without major institutional
interference from the local Curia or the Roman Curia", while devotional
literature reports a negative response in that period without producing the
document. The one Church act that *is* documented is recent: the Bishop of
Pesqueira's recognition of "presumíveis aparições" and the opening of a
diocesan phase concerning Irmã Adélia. Those are separate objects of judgment —
the apparitions, the devotion, and a person's cause — and the dataset keeps
them separate.

This is a **thin-sourcing subject**. Much of the accessible literature is
devotional and recycles itself; several dates rest on a single devotional source
and are flagged in-page with a `?`. Provenance chains are noted where a source
is derivative rather than documentary.

## Open questions

- The 1930s–40s diocesan response: does a document exist, and where? The
  diocesan archive of Pesqueira is the obvious place and is not online.
- Exact 1936 apparition dates, and whether the reports continue into 1937 (the
  accounts differ).
- The seers' biographical dates beyond what the devotional literature asserts.
- Whether any Roman act touches the case at all.

## Scope discipline

Cimbres sits inside the demarcated **Xukuru Indigenous Land** on the Serra do
Ororubá, and the shrine's history intersects with Xukuru history. This repo
stays on the apparition, the Church's response, and the shrine. Xukuru political
history — the 1998 assassination of Chicão Xukuru, the land-demarcation
conflict, the Inter-American Court judgment — is context, cited only where a
dated event here actually requires it. It is not this repo's subject.

## For agents

Read `AGENTS.md` first. Any change to `data/*.json` goes through the data-edit
gate: `node scripts/validate-data.js && node --test && node build.js`, then read
the rendered `docs/en`, `docs/es` and `docs/pt` pages before committing. Data and
regenerated `docs/` are committed together.
