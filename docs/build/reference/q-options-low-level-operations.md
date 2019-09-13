---
title: /Q-Optionen (Operationen auf niedriger Ebene)
ms.date: 01/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 6348226aa38d1f2eefdf9e19e27c4c87bd2f0812
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927675"
---
# <a name="q-options-low-level-operations"></a>/Q-Optionen (Operationen auf niedriger Ebene)

Mit den **/Q** -Compileroptionen können Sie die folgenden Compilervorgänge auf niedriger Ebene ausführen:

- [/Qfast_transcendentals (Erzwingen von schnellen transzendenten)](qfast-transcendentals-force-fast-transcendentals.md): Generiert schnelle Transzendente.

- [/QIfist (_ftol unterdrücken)](qifist-suppress-ftol.md): Unterdrückt `_ftol` , wenn eine Konvertierung von einem Gleit kommatyp in einen ganzzahligen Typ erforderlich ist (nur x86).

- [/Qimprecise_fwaits (Remove-Vorgänge in try-Blöcken entfernen)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): Entfernt `fwait` -Befehle in `try` -Blöcken.

- [/QPAR (Auto-parallelizer)](qpar-auto-parallelizer.md): Ermöglicht automatische Parallelisierung von Schleifen, die mit der [#pragma loop()](../../preprocessor/loop.md) -Direktive gekennzeichnet sind.

- [/QPAR-Report (Berichts Ebene für automatisches parallelizer)](qpar-report-auto-parallelizer-reporting-level.md): Aktiviert die Berichterstellungsebenen für die automatische Parallelisierung.

- [/Qsafe_fp_loads](qsafe-fp-loads.md): Unterdrückt Optimierungen für Gleit Komma Register Ladungen und für Verschiebungen zwischen Arbeitsspeicher und MMX-Registern.

- [/Qspectre](qspectre.md): Generiert Anweisungen, um bestimmte Spectre-Sicherheitsrisiken zu mindern.

- [/Qvec-Report (Bericht Ebene für automatische Vektorisierung)](qvec-report-auto-vectorizer-reporting-level.md): Aktiviert die Berichterstellungsebenen für die automatische Vektorisierung.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
