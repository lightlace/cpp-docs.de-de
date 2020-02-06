---
title: /Q-Optionen (Operationen auf niedriger Ebene)
ms.date: 01/08/2020
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 722a63a43e5e08fe80b26f908c7ae92df2fdb29c
ms.sourcegitcommit: 0f4ee9056d65043fa5a715f0ad1031c0ed30e2b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2020
ms.locfileid: "77034518"
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

- [/Qspectre-Load](qspectre-load.md): generiert Anweisungen zur Entschärfung von Spectre-Sicherheitsrisiken auf der Grundlage von Belastungen.

- [/Qspectre-Load-CF](qspectre-load-cf.md): generiert Anweisungen zur Abwehr von Spectre-Sicherheitsrisiken basierend auf Ablauf Steuerungs Anweisungen, die geladen werden.

- [/Qvec-Report (Auto-Vectorizer-Berichts Ebene)](qvec-report-auto-vectorizer-reporting-level.md): aktiviert Berichterstattungs Ebenen für die automatische Vektorisierung.

## <a name="see-also"></a>Weitere Informationen

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
