# cimbres — Nossa Senhora das Graças de Cimbres, a chronology

An open, source-referenced chronology of the **reported 1936 Marian
apparitions at Cimbres** (Pesqueira, Pernambuco, Brazil), of the Catholic
Church's response to them, and of the shrine and pilgrimage that grew at the
site. Part of the [cronologia](https://github.com/cronologia) family.

Published site: <https://cronologia.github.io/cimbres/> (en / es / pt).

## Posture

The apparitions are recorded as **reported** events: the dataset documents who
reported what and when, and what Church authorities ruled and when — it never
asserts the supernatural claim as fact. The Church-status finding is the
spine of the repo:

- **1936–1940s:** a diocesan inquiry (Fr. José Kehrle, for Bishop Adalberto
  Accioli Sobral) ended in a favorable but **unpublished** opinion; **no
  formal diocesan ruling — negative or positive — has been located** for that
  period. The 2023 academic study of the case (RBHR/ANPUH) describes informal
  dismissal and "silencing" instead of a decree.
- **2 October 2021:** Bishop José Luiz Ferreira Salles of Pesqueira published
  a pastoral letter recognizing the "presumíveis aparições" (presumed
  apparitions) as showing "great probability of supernatural character" and
  permitting the devotion — a **diocesan** act, not a papal one.
- **2024:** the Dicastery for the Causes of Saints granted the *nihil obstat*
  for the beatification cause of the seer Irmã Adélia (Maria da Luz), who is
  now a Servant of God. That act concerns her cause, not the apparitions.

Sourcing on this subject is thin and largely devotional; single-source dates
are flagged (`dateVerified: false`, rendered with a `?`).

## How it works

`data/chronology.json` is the source of truth. A zero-dependency Node script
compiles it into static HTML (`docs/`, served by GitHub Pages) in English
(authoritative), Spanish and Portuguese; the es/pt strings live in
`data/i18n/` as committed, hand-authored dictionaries.

```
node scripts/validate-data.js   # schema + citation check
node --test                     # invariants, i18n completeness, renderers
node build.js                   # regenerate docs/
```

Every data change must pass all three and commit the regenerated `docs/`
together with the data. See `AGENTS.md` and `context.md` before editing.

## License and corrections

Content compiled from public sources, each cited in the site's References
section. Corrections against primary sources are welcome — open an issue.
