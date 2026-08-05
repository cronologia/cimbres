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

## Current state (2026-08, after the video-mining and widening wave)

- 31 events, 10 figures, 32 references, plus facts, organizations, a
  disambiguation block and an `approvalLadder`.
- **Scope widened** per core#71: the chronology now runs from the 1676
  Oratorian mission and the colonial Vila de Cimbres, through the erection of
  the diocese (1910) and the state of it in 1936, to the 1936–37 sequence in
  more detail, and on to Kehrle's death, the seers' later lives and deaths, the
  shrine as it now stands, the 2023 transfer of Irmã Adélia's papers and the
  Roman phase of her cause.
- **Reported miracles are recorded as reports, never as events that happened.**
  A `Reported cures` fact and a disambiguation item say so; the earliest cure
  testimony that can be dated (31 August 1985) is recorded as a report with its
  reporter; no cure at Cimbres has been recognised by any authority, and cures
  get no approval-ladder rung.
- The **approval ladder** renders at the top of every page, five rungs, one per
  authority. The statuses are unchanged by this wave: the 1930s–40s diocesan
  rung is still `reported-undocumented`, Rome on the apparitions is still
  `not-found`.
- Three locales (en / es / pt) built from `data/chronology.json`; the es and pt
  dictionaries are exact-key, hand-authored by the assistant and **not**
  human-reviewed (`_meta.humanReviewed: false`, and the page banner says so).
  179 translatable strings per locale, zero missing, zero stale.
  `organizations[].founded` was added to `TRANSLATABLE_KEYS` in this wave: it
  renders ("Fundada em …") and was leaving four English clauses on both
  localized pages.
- Gate green: `validate-data.js`, `build.js`, `node --test` (153).

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

The 2016 UNICAP dissertation adds a checked zero of its own that is worth
repeating: it found no coverage of the events in the *Jornal do Commercio* or
the *Diário de Pernambuco* for August–November 1936.

This is a **thin-sourcing subject**. Much of the accessible literature is
devotional and recycles itself; several dates rest on a single devotional source
and are flagged in-page with a `?`. Provenance chains are noted where a source
is derivative rather than documentary — including that the lead author of the
2023 academic study, Carlos André Silva de Moura, is president of the
historical and archival commission of Irmã Adélia's beatification cause.

The devotional **bibliography behind the videos** is now identified and cited:
Paiva, *Aqui o Céu encontra-se com a Terra* (1987/1990, 10th ed. 2024); Lira,
*O Diário do Silêncio* (2018) and *O Inquisidor de Cimbres* (2021); Silva,
*Eu sou a Graça* (2016); and the one academic addition, Aguiar Neto's UNICAP
dissertation (2016). Videos are in `references[]`, perspective-labeled as
devotional commentary, and are cited only for attributed positions.

## Open questions

- The 1930s–40s diocesan response: does a document exist, and where? Three
  archives would settle it and none has been consulted — the diocesan archive
  of Pesqueira (Kehrle's manuscript); the papers of the Pesqueira police
  delegacy and the Pernambuco chefia de polícia, where an order for the 20
  October 1936 detention of Artur Teixeira would be; and the Irmã Adélia
  collection at the Instituto RIC in Recife since July 2023.
- **Kehrle's diary may already be in print.** Ana Lígia Lira's *O Inquisidor de
  Cimbres* (Apascentar, 2021) is presented by its author as a full
  transcription of the diary and of Maria da Luz's letters, and Ione Paiva's
  *Aqui o Céu encontra-se com a Terra* reproduces its material. Neither has been
  read here. Collating them against the archive copy is the single most
  valuable next step on this subject.
- The sanctuary decree. The received date, 20 October 1998, is attributed to a
  bishop who left office on 26 May 1993. Either the year or the bishop is wrong;
  Ione Paiva says 1988 and says the signed decree is printed in her book.
- Exact 1936–37 apparition dates. The 2016 UNICAP dissertation gives 26 February
  1937 for the last at Sítio Guarda; the devotional accounts disagree with each
  other and with it.
- Whether any Roman act touches the case at all. The tradition's own leading
  researcher says on camera that she has no evidence of one.

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
