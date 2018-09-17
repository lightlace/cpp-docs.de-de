---
title: -Q-Optionen (Operationen auf niedriger Ebene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /q
dev_langs:
- C++
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15854333a9f26f87d20f7819327e68050ab37bf6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717779"
---
# <a name="q-options-low-level-operations"></a>/Q-Optionen (Operationen auf niedriger Ebene)

Sie können die **/q /** Compileroptionen, die zum Ausführen der folgenden Compilervorgänge:

- [/ Qfast_transcendentals (Erzwingen von schnellen transzendenten)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): generiert schnelle Transzendente.

- [/ QIfist (_ftol unterdrücken)](../../build/reference/qifist-suppress-ftol.md): unterdrückt `_ftol` Wenn eine Konvertierung von einem Gleitkommatyp in Ganzzahltyp ist erforderlich (nur X86).

- [/ Qimprecise_fwaits (Entfernen von Fwaits in Try-Blöcken)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): entfernt `fwait` -Befehle in `try` Blöcke.

- [/ Qpar (automatische Parallelisierung)](../../build/reference/qpar-auto-parallelizer.md): ermöglicht automatische Parallelisierung von Schleifen, die mit markierten Felder der [#pragma loop()](../../preprocessor/loop.md) Richtlinie.

- [/ Qpar-Report (Auto-Parallelizer-Berichtsebene)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): aktiviert die Berichterstellungsebenen für die automatische Parallelisierung.

- [/ Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): unterdrückt Optimierungen aus, für die Gleitkommaregister lädt und für Verschiebungen zwischen Arbeitsspeicher und MMX registriert wird.

- [/ Qspectre](../../build/reference/qspectre.md): generiert Anweisungen, um bestimmte Spectre-Sicherheitsrisiken zu verringern.

- [/ Qvec-Report (Auto-Vektorisierer Berichtsebene)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): aktiviert die Berichterstellungsebenen für die automatische Vektorisierung.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
