---
title: Compilerwarnung (Stufe 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: 24a3ca8b35266e93f298314f45015b7a480e2af0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397288"
---
# <a name="compiler-warning-level-1-c4561"></a>Compilerwarnung (Stufe 1) C4561

"__fastcall" nicht kompatibel mit der "/ Clr" Option: Konvertieren in "\__stdcall"

Die [__fastcall](../../cpp/fastcall.md) funktionsaufrufkonvention kann nicht verwendet werden, mit der ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) -Compileroption. Der Compiler ignoriert die Aufrufe von `__fastcall`. Um diese Warnung zu beheben, entfernen Sie entweder die Aufrufe an **__fastcall** oder Kompilieren Sie ohne **"/ CLR"**.

Im folgende Beispiel wird die C4561 generiert:

```
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```