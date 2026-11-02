# How this repository was made (Vitória da Conquista)

This file is written by the build on 2026-11-02, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Câmara Municipal de Vitória da Conquista, SAPL: the Lei Orgânica of 28 November 2025 (PDF) | <https://sapl.vitoriadaconquista.ba.leg.br/norma/4538> | 2026-11-02 | Texts: Câmara Municipal de Vitória da Conquista, SAPL (Sistema de Apoio ao Processo Legislativo), sapl.vitoriadaconquista.ba.leg.br; SAPL: "Conteúdo e dados sob licença Creative Commons 4.0 Atribuir Fonte - Compartilhar Igual". Lei 9.610/1998 art. 8 IV: the texts of laws and other official acts are not protected by copyright. Non-official text: only the official gazette is authoritative. |
| Câmara Municipal de Vitória da Conquista, SAPL: scanned PDFs of municipal laws, read by OCR | <https://sapl.vitoriadaconquista.ba.leg.br/norma/pesquisar> | 2026-11-02 | Texts: Câmara Municipal de Vitória da Conquista, SAPL (Sistema de Apoio ao Processo Legislativo), sapl.vitoriadaconquista.ba.leg.br; SAPL: "Conteúdo e dados sob licença Creative Commons 4.0 Atribuir Fonte - Compartilhar Igual". Lei 9.610/1998 art. 8 IV: the texts of laws and other official acts are not protected by copyright. Non-official text: only the official gazette is authoritative. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `lei-organica` | Lei Orgânica do Município de Vitória da Conquista | 1 | 2025-12-01 to 2025-12-01 |
| `lei-2026-03227` | Lei nº 3.227, de 2 de outubro de 2026 | 1 | 2026-10-02 to 2026-10-02 |
| `lei-2026-03214` | Lei nº 3.214, de 22 de setembro de 2026 | 1 | 2026-09-23 to 2026-09-23 |
| `lei-2026-03194` | Lei nº 3.194, de 14 de setembro de 2026 | 1 | 2026-09-14 to 2026-09-14 |
| `lei-2026-03191` | Lei nº 3.191, de 3 de setembro de 2026 | 1 | 2026-09-03 to 2026-09-03 |

The build made 5 commits:

| Commits | Kind |
| ---: | --- |
| 5 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `futuro`: laws not yet in force on 2026-11-02.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 5 laws in the record.
- 10 tags.

## Dates

Each commit is dated at noon (America/Bahia) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: The Lei Orgânica of 28 November 2025 says (art. 360) that it takes effect on its publication; this record dates it by the publication date SAPL records (1 December 2025). Municipal laws: Decreto-Lei 4.657/1942 (LINDB) art. 1 gives 45 days unless a law says otherwise; this record takes in only laws whose vigência clause says they take effect on their publication (or signature) and dates each by the publication date SAPL records for it (else by its date). https://sapl.vitoriadaconquista.ba.leg.br/norma/4538

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `c74a6d977b904db3c881a8ff8c5f48c9f8f4c747065a147cf0667917e60e058c` (352346 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `900da0d33bfd1ef455267fb4dcef7961fd5acc9c`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

5 versions of 5 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- The Lei Orgânica is the new wording promulgated on 28 November 2025 (Emenda à Lei Orgânica nº 001/2025, "Dá nova redação à Lei Orgânica"), as promulgated, from the PDF the Câmara's SAPL holds, dated by the publication date SAPL records (art. 360: in force on its publication). The Lei Orgânica of 2007 it revoked, and any amendment after it, are not in this record.
- The PDF is read line by line: the table of contents before the text and the signatures after the closing line ("Vitória da Conquista – BA, 28 de novembro de 2025.") are left out, as are page numbers. Lines are joined into paragraphs (a new paragraph at a provision label, a heading line, or after a line ending in ".", ";" or ":"). One file per Art.; headings stand above the first article under them.
- Each municipal law ("Lei" and "Lei Complementar") is given as enacted, from the PDF the Câmara's SAPL holds for it, credited to the law itself and dated by the publication date SAPL records for it (else by the law's own date). Later amendments by other laws are not worked into earlier laws: each law is its own file set as enacted. Laws are taken newest first, in parts.
- Left out: scans (with or without an OCR layer), PDFs whose heading does not carry the record's number, texts with no article or no closing date line, texts carrying alteration notes, and laws whose vigência clause sets another day than their publication (or that have none, so that the 45 days of the LINDB apply).
- The text runs from the law's heading to its closing date line (signatures after it are left out); lines repeated at the top or bottom of two or more pages (letterheads, footers) and page numbers are left out. Lines are joined into paragraphs: a new paragraph starts at a provision label, a heading line, or after a line ending in ".", ";" or ":". One file per Art.; "000-titulo" holds what comes before the first article.
- 40-ocr-001: 4 municipal laws read by OCR from the scanned PDFs the Câmara's SAPL holds (Alan's decision D8, 2026-11-02: OCR is allowed for official scans whose terms allow reuse, marked as OCR and spot-checked). Reader: Tesseract 5.4.0, language model "por" (tessdata_best), --psm 3, pages rendered at 300 dpi; the city's Lexifina's code rules (heading, articles, closing date line, alteration notes, vigência, dates, furniture and page numbers) apply unchanged. Every file of an OCR'd law starts with a front-matter line "Text-source: OCR (...) of the official scan <url>", and its commit message says the same. Spot-check (instead of the letters check with a second PDF reader, which needs a text layer): for every law in the part, 3 paragraphs drawn at random are cut out of the scan and read again with a different setting (tessdata_fast, --psm 6); a law with any paragraph under 98% character agreement is left out. Also left out: a law with any paragraph holding 3 or more OCR-noise tokens, or with a publication stamp ("PREF. MUN.", "Publicado no DOM") read into its text. Agreement in this part: lowest law 99.75%, mean 99.87%. OCR can misread single characters; for anything that matters, read the scan.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (claude-opus-5-5) wrote Lexifina's code and chose the sources. No model output is used as legal text or dates: every word comes from the Câmara's SAPL.
- Claude Code (claude-opus-5-5) wrote Lexifina's code and chose the sources. No model output is used as legal text or dates: every word comes from the Câmara's SAPL.
- Where a PDF is a scan, its words are read by Tesseract OCR, not by a language model.
