---
title: Compilerwarnung (Stufe 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: b0fd27142f0404a53fa2fee87fb2309e2f54d2c2
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965980"
---
# <a name="compiler-warning-level-1-c4561"></a>Compilerwarnung (Stufe 1) C4561

' __fastcall ' ist nicht kompatibel mit der Option '/CLR ': die Umstellung auf '\__stdcall '

Die [__fastcall](../../cpp/fastcall.md) -Funktionsaufruf Konvention kann nicht mit der [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) -Compileroption verwendet werden. Der Compiler ignoriert die Aufrufe an `__fastcall`. Um diese Warnung zu beheben, entfernen Sie entweder die Aufrufe von **__fastcall** oder Kompilieren ohne **/CLR**.

Im folgenden Beispiel wird C4561 generiert:

```cpp
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```