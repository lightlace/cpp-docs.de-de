---
title: Compilerwarnung (Stufe 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: 13c56c2261cd069e7edec63921c198e2bee56c95
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626697"
---
# <a name="compiler-warning-level-1-c4272"></a>Compilerwarnung (Stufe 1) C4272

"Function": ist als __declspec (dllimport) markiert. beim Importieren einer Funktion muss eine native Aufruf Konvention angegeben werden.

Es ist ein Fehler, eine Funktion zu exportieren, die mit der [__clrcall](../../cpp/clrcall.md) -Aufruf Konvention gekennzeichnet ist, und der Compiler gibt diese Warnung aus, wenn Sie versuchen, eine als `__clrcall`markierte Funktion zu importieren.

Im folgenden Beispiel wird C4272 generiert:

```cpp
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```