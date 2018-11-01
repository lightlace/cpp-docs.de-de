---
title: Compilerwarnung (Stufe 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: c585294686298a1197d437d41a0d541f1268985f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512735"
---
# <a name="compiler-warning-level-3-c4290"></a>Compilerwarnung (Stufe 3) C4290

C++-Ausnahmespezifikation ignoriert, es sei denn, so dass eine Funktion ist nicht __declspec(nothrow).

Eine Funktion wird deklariert, mit der Ausnahmespezifikation, die Visual C++ akzeptiert, aber nicht implementiert. Code mit der Ausnahme, die Spezifikationen, die während der Kompilierung ignoriert werden neu kompiliert werden können und verknüpft sein wiederverwendet in zukünftigen Versionen, die Ausnahmespezifikationen unterstützen.

Weitere Informationen finden Sie unter [Ausnahmespezifikationen (Throw)](../../cpp/exception-specifications-throw-cpp.md) .

Sie können diese Warnung vermeiden, indem die [Warnung](../../preprocessor/warning.md) Pragma:

```
#pragma warning( disable : 4290 )
```

Im folgenden Codebeispiel wird die C4290 generiert:

```
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```