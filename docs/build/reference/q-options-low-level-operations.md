---
title: /Q-Optionen (Operationen auf niedriger Ebene)
ms.date: 01/08/2020
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 9dd3675f200be4f0ec66620bcf3cf05706991b66
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518170"
---
# <a name="q-options-low-level-operations"></a>/Q-Optionen (Operationen auf niedriger Ebene)

Mit den **/Q** -Compileroptionen können Sie die folgenden Compilervorgänge auf niedriger Ebene ausführen:

- [/Qfast_transcendentals (Erzwingen von schnellen transzendenten)](qfast-transcendentals-force-fast-transcendentals.md): generiert schnelle transzendente.

- [/QIfist (unterdrücken von _ftol)](qifist-suppress-ftol.md): unterdrückt `_ftol`, wenn eine Konvertierung von einem Gleit kommatyp in einen ganzzahligen Typ erforderlich ist (nur x86).

- [/Qimprecise_fwaits (Remove-Vorgänge in try-Blöcken)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): entfernt `fwait` Befehle innerhalb von `try`-Blöcken.

- [/QIntel-JCC-Erratum](qintel-jcc-erratum.md): verringert die Leistungseinbußen, die durch den Intel Jump Conditional Code (JCC)-Erratum-mikrocodeupdate verursacht werden.

- [/QPAR (Auto-parallelizer)](qpar-auto-parallelizer.md): ermöglicht die automatische Parallelisierung von Schleifen, die mit der [#pragma Loop ()](../../preprocessor/loop.md) -Direktive gekennzeichnet sind.

- [/QPAR-Report (Berichts Ebene mit automatischer Parallelisierung)](qpar-report-auto-parallelizer-reporting-level.md): aktiviert Berichterstattungs Ebenen für die automatische Parallelisierung.

- [/Qsafe_fp_loads](qsafe-fp-loads.md): unterdrückt Optimierungen für Gleit Komma Register Ladevorgänge und für Verschiebungen zwischen Arbeitsspeicher und MMX-Registern.

- [/Qspectre](qspectre.md): generiert Anweisungen, um bestimmte Spectre-Sicherheitslücken zu mindern.

- [/Qvec-Report (Auto-Vectorizer-Berichts Ebene)](qvec-report-auto-vectorizer-reporting-level.md): aktiviert Berichterstattungs Ebenen für die automatische Vektorisierung.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
