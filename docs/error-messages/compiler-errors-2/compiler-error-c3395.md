---
title: Compilerfehler C3395
ms.date: 11/04/2016
f1_keywords:
- C3395
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
ms.openlocfilehash: 2e5234abcbe46e17035fd0b16e9816c879d86cfe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604115"
---
# <a name="compiler-error-c3395"></a>Compilerfehler C3395

"Function": __declspec(dllexport) kann nicht angewendet werden, um eine Funktion mit dem \__clrcall-Aufrufkonvention

`__declspec(dllexport)` und [__clrcall](../../cpp/clrcall.md) sind nicht kompatibel.  Weitere Informationen finden Sie unter [Dllexport, Dllimport](../../cpp/dllexport-dllimport.md).

Im folgende Beispiel wird die C3395 generiert:

```
// C3395.cpp
// compile with: /clr /c

__declspec(dllexport) void __clrcall Test(){}   // C3395
void __clrcall Test2(){}   // OK
__declspec(dllexport) void Test3(){}   // OK
```