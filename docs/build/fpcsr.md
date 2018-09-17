---
title: FpCsr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6ed0500d0382563878d0751ba5386e4cc637fdb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718288"
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