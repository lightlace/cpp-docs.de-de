---
title: MxCsr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d18a4247d36e6894230d74322d52cd5854e42fb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726504"
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