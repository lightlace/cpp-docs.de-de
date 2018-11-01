---
title: 2.1 Anweisungsformat
ms.date: 11/04/2016
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
ms.openlocfilehash: 6ee977005d421a59e71f852be3d78a2caad9b45b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629488"
---
# <a name="21-directive-format"></a>2.1 Anweisungsformat

Die Syntax einer OpenMP-Direktive wird offiziell angegeben, indem die Grammatik in [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md), informell wie folgt:

```
#pragma omp directive-name  [clause[ [,] clause]...] new-line
```

Jede Anweisung beginnt mit **#pragma Omp**, um das Potenzial für einen Konflikt mit anderen (nicht-OpenMP oder Anbieter-Erweiterungen mit OpenMP)-Pragma-Direktiven mit den gleichen Namen zu reduzieren. Der Rest der Anweisung folgt die Konventionen der C- und C++-Standards für Compiler-Direktiven. Insbesondere Leerraum kann verwendet werden vor und nach der **#**, und manchmal darf Leerzeichen verwendet werden, um die Wörter in einer Anweisung zu trennen. Vorverarbeitungstoken befolgen die **#pragma Omp** makroersetzung unterliegen.

Richtlinien beachtet werden. Die Reihenfolge der Klauseln in Anweisungen ist nicht erheblich. Klauseln auf Anweisungen können wiederholt werden, bei Bedarf gemäß den Einschränkungen, die in der Beschreibung der einzelnen Klauseln aufgeführt. Wenn *Variablenliste* wird in einer Klausel nur Variablen angegeben werden muss. Nur ein *Richtlinie-Name* kann pro Richtlinie angegeben werden.  Die folgende Anweisung ist z. B. nicht zulässig:

```
/* ERROR - multiple directive names not allowed */
#pragma omp parallel barrier
```

Eine OpenMP-Direktive gilt für höchstens einer nachfolgenden Anweisung, die einem strukturierten Block sein muss.