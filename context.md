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

- 13 events, 6 figures, 14 references, plus facts, organizations, a
  disambiguation block and an `approvalLadder`.
- The **approval ladder** (adopted from the core template, 2026-08) renders at
  the top of every page: five rungs, one per authority, with the shape of the
  finding visible in it — a documented favourable investigators' report, a
  1930s–40s bishop's ruling that is `reported-undocumented`, the 2021 pastoral
  letter, `not-found` for Rome on the apparitions, and Irmã Adélia's cause as a
  separate object. It never renders an overall verdict for the case.
- The diocese's own 2021 **carta pastoral** is now cited as a primary source
  (`carta-pastoral-2021`, PDF on the diocesan CDN). It supplies the letter's
  verbatim wording, confirms Sobral's 1934–1947 episcopate and the investigators'
  "parecer favorável", records the ecclesiastical silencing and the 1936 police
  detention of Maria da Luz's father — and calls itself "a primeira resposta da
  Igreja", the strongest evidence reached that no earlier ruling exists.
- Three locales (en / es / pt) built from `data/chronology.json`; the es and pt
  dictionaries are exact-key, hand-authored by the assistant and **not**
  human-reviewed (`_meta.humanReviewed: false`, and the page banner says so).
  102 translatable strings per locale, zero missing, zero stale.
- Gate green: `validate-data.js`, `node --test` (153), `build.js`.

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

The approval ladder is where that separation is now visible. The 1930s–40s
diocesan rung is `reported-undocumented`, **never** `negative`: a ruling is
reported and no document has been located, and those are different claims. The
Rome rung is `not-found` and deliberately not `not-reached` — the first is a
statement about the evidence this project has reached, the second would be a
claim about the case, and settling it would take dicastery registers nobody
here has seen. Irmã Adélia's cause has its own rung, labelled as a different
object, so that a judgment about a person cannot be read as approval of the
apparitions.

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
