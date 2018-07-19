---
title: -Q-Optionen (Operationen auf niedriger Ebene) | Microsoft Docs
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
ms.openlocfilehash: c8a18c5d790cf21e8eb130a2b2baa152e20d79a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375034"
---
# <a name="q-options-low-level-operations"></a>/Q-Optionen (Operationen auf niedriger Ebene)

Sie können die **/q /** -Compileroptionen zur Durchführung der folgenden Compilervorgänge:

- [/ Qfast_transcendentals (Erzwingen von schnellen transzendenten)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): generiert schnelle Transzendente.

- [/ QIfist (_ftol unterdrücken)](../../build/reference/qifist-suppress-ftol.md): unterdrückt `_ftol` Wenn eine Konvertierung von einem Gleitkommatyp zu einem ganzzahligen Typ erforderlich (nur X86) ist.

- [/ Qimprecise_fwaits (Entfernen von Fwaits in Try-Blöcken)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): entfernt `fwait` -Befehle in `try` blockiert.

- [/ Qpar (automatische Parallelisierung)](../../build/reference/qpar-auto-parallelizer.md): ermöglicht automatische Parallelisierung von Schleifen, die mit markiert sind die [#pragma loop()](../../preprocessor/loop.md) Richtlinie.

- [/ Qpar-Report (Auto-Parallelisierer Reporting Stufe)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): aktiviert die Berichterstellungsebenen für die automatische Parallelisierung.

- [/ Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): unterdrückt Optimierungen für Gleitkommaregister lädt und für wechselt zwischen Arbeitsspeicher und MMX registriert.

- [/ Qspectre](../../build/reference/qspectre.md): generiert Anweisungen, um bestimmte Absorptionsspektrum Sicherheitsrisiken zu minimieren.

- [/ Qvec-Report (Auto-Vektorisierer Reporting Stufe)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): aktiviert die Berichterstellungsebenen für die automatische Vektorisierung.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
