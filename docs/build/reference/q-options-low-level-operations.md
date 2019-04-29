---
title: /Q-Optionen (Operationen auf niedriger Ebene)
ms.date: 1/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 5bbb63b4f437f8aefd5c84c1c1c4bd20bdb965cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319394"
---
# <a name="q-options-low-level-operations"></a>/Q-Optionen (Operationen auf niedriger Ebene)

Sie können die **/q /** Compileroptionen, die zum Ausführen der folgenden Compilervorgänge:

- [/ Qfast_transcendentals (Erzwingen von schnellen transzendenten)](qfast-transcendentals-force-fast-transcendentals.md): Generiert schnelle Transzendente.

- [/QIfist (Suppress _ftol)](qifist-suppress-ftol.md): Unterdrückt die `_ftol` Wenn eine Konvertierung von einem Gleitkommatyp in Ganzzahltyp ist erforderlich (nur X86).

- [/ Qimprecise_fwaits (Entfernen von Fwaits in Try-Blöcken)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): Entfernt `fwait` -Befehle in `try` -Blöcken.

- [/ Qpar (automatische Parallelisierung)](qpar-auto-parallelizer.md): Ermöglicht automatische Parallelisierung von Schleifen, die mit der [#pragma loop()](../../preprocessor/loop.md) -Direktive gekennzeichnet sind.

- [/ Qpar-Report-(Auto-Parallelizer-Berichtsebene)](qpar-report-auto-parallelizer-reporting-level.md): Aktiviert die Berichterstellungsebenen für die automatische Parallelisierung.

- [/Qsafe_fp_loads](qsafe-fp-loads.md): Unterdrückt Optimierungen beim Laden von Gleitkommaregistern und für Verschiebungen zwischen Arbeitsspeicher und MMX-Registern.

- [/Qspectre](qspectre.md): Generiert die Anweisungen, um bestimmte Spectre-Sicherheitsrisiken zu verringern.

- [/ Qvec-Report (Auto-Vektorisierer Berichtebene)](qvec-report-auto-vectorizer-reporting-level.md): Aktiviert die Berichterstellungsebenen für die automatische Vektorisierung.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
