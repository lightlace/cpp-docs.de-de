---
title: MxCsr
ms.date: 11/04/2016
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
ms.openlocfilehash: d411223634aec6d11413ac1f5b1fb04dba7498e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497372"
---
# <a name="mxcsr"></a>MxCsr

Der Registerstatus enthält auch MxCsr. Die Aufrufkonvention teilt dieses Register, in einen flüchtigen und einen nicht flüchtigen Teil. Der flüchtige Teil besteht aus den 6-Statusflags MXCSR [0:5], während die restlichen das Register, MXCSR [6:15] flüchtig ist.

Der Teil wird zu Beginn der Ausführung des Programms auf die folgenden Standardwerte festgelegt:

```
MXCSR[6]         : Denormals are zeros - 0
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)
```

Eine aufgerufene Funktion, die die nicht flüchtige Felder im MXCSR ändert, muss diese vor der Rückgabe an den Aufrufer wiederherstellen. Darüber hinaus muss ein Aufrufer, der keines dieser Felder geändert wurde wiederhergestellt werden ihren Standardwerten vor dem eine aufgerufene Funktion aufrufen, es sei denn, der Vereinbarung der aufgerufenen Funktion die geänderten Werte erwartet wird.

Es gibt zwei Ausnahmen von den Regeln in Bezug auf die Flüchtigkeit der Steuerelement-Kennzeichen:

- In Funktionen, in dem dokumentiert die angegebene Funktion dient, nicht flüchtiger MxCsr-flags.

- Wenn Programmanalyse korrigieren Sie den Verstoß gegen diese Regeln ein Programm, das ein Programm, in denen diese Regeln nicht, z. B. durch Analyse des gesamten Programms verletzt werden, identisch verhält sich/bedeutet führt.

Keine Annahmen können über den Status des flüchtigen Teils des MXCSR funktionsübergreifend, vorgenommen werden, es sei denn, insbesondere in der Dokumentation der Funktion beschrieben.

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)