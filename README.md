# Vitória da Conquista (city): law history in git

The municipal law of the Município de Vitória da Conquista, Bahia (Brazil) as a git history: one file per Artigo, one paragraph per line, so `git blame`, `git log` and `git diff` work line by line. The text is Portuguese, the only official language.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

## What this repository holds

| Folder | Act | Versions |
| --- | --- | ---: |
| `lei-organica/` | Lei Orgânica do Município de Vitória da Conquista, de 28 de novembro de 2025 | 1 (as promulgated) |

**The Lei Orgânica.** The Lei Orgânica is the new wording promulgated on 28 November 2025 (Emenda à Lei Orgânica nº 001/2025, "Dá nova redação à Lei Orgânica"), as promulgated, from the PDF the Câmara's SAPL holds, dated by the publication date SAPL records (art. 360: in force on its publication). The Lei Orgânica of 2007 it revoked, and any amendment after it, are not in this record.

State law is in [brazil-bahia-law](https://github.com/lexifina/brazil-bahia-law); federal law is in [brazil-law](https://github.com/lexifina/brazil-law).

## Source

[Câmara Municipal de Vitória da Conquista, SAPL](https://sapl.vitoriadaconquista.ba.leg.br/norma/4538), published by the Câmara Municipal de Vitória da Conquista. Each version names the page it was taken from and that page's sha256, in `data/versions.json`.

## Dates

The Lei Orgânica of 28 November 2025 says (art. 360) that it takes effect on its publication; this record dates it by the publication date SAPL records (1 December 2025). Commits are at noon in Vitória da Conquista.

## How it is built

Lexifina reads the sources listed here and records each act's dated versions, and the laws that made each change, in one corpus file. `tools/build.py` writes this repository from that file, and the same corpus always gives the same commit hashes; `REPRODUCE.md` gives the details and the checks. A model (Claude) wrote Lexifina's code; it wrote no legal text, and no model runs when the history is built.

The PDF is read line by line: the table of contents before the text and the signatures after the closing line ("Vitória da Conquista – BA, 28 de novembro de 2025.") are left out, as are page numbers. Lines are joined into paragraphs (a new paragraph at a provision label, a heading line, or after a line ending in ".", ";" or ":"). One file per Art.; headings stand above the first article under them.

## How it is checked

Every version is read back from git on the day it took effect (`tools/check_repo.py`) and must match the corpus; an independent letters-and-digits comparison of every version against the source page must show no difference. Results are in `REPRODUCE.md`.

## What "author" means

The author of each commit is the law that made the text, or, for a consolidated text, the publisher, with an e-mail address that cannot exist; the committer is always Lexifina.

## Limits

The record is SAPL's: a version is only as exact as the Câmara's text for it. Ordinary and complementary laws are not in yet. The text is not the official version: only the Diário Oficial do Município is authoritative.

## Licence

See [LICENSE](LICENSE): Brazilian law texts are not protected by copyright (Lei 9.610/1998, art. 8, IV). Fonte: Câmara Municipal de Vitória da Conquista, SAPL, Câmara Municipal de Vitória da Conquista.
