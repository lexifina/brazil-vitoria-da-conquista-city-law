# How this repository was made (Vitória da Conquista)

This file is written by the build on 2026-11-02, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Câmara Municipal de Vitória da Conquista, SAPL: the Lei Orgânica of 28 November 2025 (PDF) | <https://sapl.vitoriadaconquista.ba.leg.br/norma/4538> | 2026-11-02 | Texts: Câmara Municipal de Vitória da Conquista, SAPL (Sistema de Apoio ao Processo Legislativo), sapl.vitoriadaconquista.ba.leg.br; SAPL: "Conteúdo e dados sob licença Creative Commons 4.0 Atribuir Fonte - Compartilhar Igual". Lei 9.610/1998 art. 8 IV: the texts of laws and other official acts are not protected by copyright. Non-official text: only the official gazette is authoritative. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `lei-organica` | Lei Orgânica do Município de Vitória da Conquista | 1 | 2025-12-01 to 2025-12-01 |

The build made 1 commits:

| Commits | Kind |
| ---: | --- |
| 1 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `futuro`: laws not yet in force on 2026-11-02.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 2 tags.

## Dates

Each commit is dated at noon (America/Bahia) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: The Lei Orgânica of 28 November 2025 says (art. 360) that it takes effect on its publication; this record dates it by the publication date SAPL records (1 December 2025). Municipal laws: Decreto-Lei 4.657/1942 (LINDB) art. 1 gives 45 days unless a law says otherwise; this record takes in only laws whose vigência clause says they take effect on their publication (or signature) and dates each by the publication date SAPL records for it (else by its date). https://sapl.vitoriadaconquista.ba.leg.br/norma/4538

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `418c7afb8307304a656d5898551c873d7286f89c414780ca16e9a3efb451346d` (331150 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3d00541d258745461ab52b1b0cb4e1716a27a95d`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

1 versions of 1 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- The Lei Orgânica is the new wording promulgated on 28 November 2025 (Emenda à Lei Orgânica nº 001/2025, "Dá nova redação à Lei Orgânica"), as promulgated, from the PDF the Câmara's SAPL holds, dated by the publication date SAPL records (art. 360: in force on its publication). The Lei Orgânica of 2007 it revoked, and any amendment after it, are not in this record.
- The PDF is read line by line: the table of contents before the text and the signatures after the closing line ("Vitória da Conquista – BA, 28 de novembro de 2025.") are left out, as are page numbers. Lines are joined into paragraphs (a new paragraph at a provision label, a heading line, or after a line ending in ".", ";" or ":"). One file per Art.; headings stand above the first article under them.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (claude-opus-5-5) wrote Lexifina's code and chose the sources. No model output is used as legal text or dates: every word comes from the Câmara's SAPL.
