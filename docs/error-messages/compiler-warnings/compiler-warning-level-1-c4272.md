---
title: Compilerwarnung (Stufe 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: 26e136aa395729d520f4a71a06b6dc212cf21f8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479989"
---
# <a name="compiler-warning-level-1-c4272"></a>Compilerwarnung (Stufe 1) C4272

'Funktion': ist als __declspec(dllimport) markiert. systemeigene Aufrufkonvention muss angegeben werden, beim Importieren einer Funktion.

Es ist ein Fehler so exportieren Sie eine Funktion mit dem [__clrcall](../../cpp/clrcall.md) Aufrufkonvention und der Compiler gibt diese Warnung, wenn Sie versuchen, eine Funktion importieren `__clrcall`.

Im folgende Beispiel wird die C4272 generiert:

```
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```