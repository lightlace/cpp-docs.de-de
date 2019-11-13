---
title: Compilerwarnung (Stufe 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: 5ccacd7d5f4dfd2e9ad8de3958d7aa43571091fe
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051660"
---
# <a name="compiler-warning-level-3-c4290"></a>Compilerwarnung (Stufe 3) C4290

C++Ausnahme Spezifikation ignoriert, außer um anzugeben, dass eine Funktion nicht __declspec (nothrow)

Eine Funktion wird mit der Ausnahme Spezifikation deklariert, die C++ von Visual akzeptiert, aber nicht implementiert wird. Code mit Ausnahme Spezifikationen, die während der Kompilierung ignoriert werden, müssen möglicherweise erneut kompiliert und verknüpft werden, damit Sie in zukünftigen Versionen unterstützt werden, die Ausnahme Spezifikationen unterstützen

Weitere Informationen finden Sie unter [Ausnahme Spezifikationen (Throw)](../../cpp/exception-specifications-throw-cpp.md) .

Sie können diese Warnung vermeiden, indem Sie das [Warning](../../preprocessor/warning.md) -Pragma verwenden:

```cpp
#pragma warning( disable : 4290 )
```

Im folgenden Codebeispiel wird C4290 generiert:

```cpp
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```