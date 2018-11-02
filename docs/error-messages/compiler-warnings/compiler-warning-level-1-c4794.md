---
title: Compilerwarnung (Stufe 1) C4794
ms.date: 11/04/2016
f1_keywords:
- C4794
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
ms.openlocfilehash: d44e3af88de9457fdc5c2df905ccbae22d3562da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464076"
---
# <a name="compiler-warning-level-1-c4794"></a>Compilerwarnung (Stufe 1) C4794

Segment der Variable 'Variable' im lokalen Thread-Speicher von 'Abschnittsname' nach '.tls$' verschoben

Sie haben [#pragma data_seg](../../preprocessor/data-seg.md) verwendet, um eine tls-Variable in einem Abschnitt zu positionieren, der nicht mit „.tls$“ beginnt.

Der Abschnitt „.tls$*x* “ befindet sich in der Objektdatei, wo die [__declspec(thread)](../../cpp/thread.md) -Variablen definiert werden. Durch diese Abschnitte ergibt sich ein „.tls“-Abschnitt in der EXE- oder DLL-Datei.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4794 generiert.

```
// C4794.cpp
// compile with: /W1 /c
#pragma data_seg(".someseg")
__declspec(thread) int i;   // C4794

// OK
#pragma data_seg(".tls$9")
__declspec(thread) int j;
```