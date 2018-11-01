---
title: FpCsr
ms.date: 11/04/2016
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
ms.openlocfilehash: 018ce39a194d5153f73fa452990844362190e6bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472816"
---
# <a name="fpcsr"></a>FpCsr

Der Registerstatus enthält auch die X87 FPU-Steuerwort. Die Aufrufkonvention schreibt vor, diese registrieren, um nicht flüchtig sein.

Ausführung des Programms die X87 FPU-Steuerelement Word Register ist am Anfang auf die folgenden Standardwerte festgelegt:

```
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)
FPCSR[7]: Reserved - 0
FPCSR[8:9]: Precision Control - 10B (double precision)
FPCSR[10:11]: Rounding  control - 0 (round to nearest)
FPCSR[12]: Infinity control - 0 (not used)
```

Eine aufgerufene Funktion, die eines der Felder in FPCSR ändert, muss diese vor der Rückgabe an den Aufrufer wiederherstellen. Darüber hinaus muss ein Aufrufer, der keines dieser Felder geändert wurde wiederhergestellt werden ihren Standardwerten vor dem eine aufgerufene Funktion aufrufen, es sei denn, der Vereinbarung der aufgerufenen Funktion die geänderten Werte erwartet wird.

Es gibt zwei Ausnahmen von den Regeln in Bezug auf die Flüchtigkeit der Steuerelement-Kennzeichen:

1. In Funktionen, in dem dokumentiert die angegebene Funktion dient, nicht flüchtiger FpCsr-flags.

1. Wenn Programmanalyse korrigieren Sie den Verstoß gegen diese Regeln ein Programm, das ein Programm, in denen diese Regeln nicht, z. B. durch Analyse des gesamten Programms verletzt werden, identisch verhält sich/bedeutet führt.

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)