---
title: Compilerfehler C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: fc2aeac02ecc3f29406c2288051ca6cd9d3a4923
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760009"
---
# <a name="compiler-error-c2346"></a>Compilerfehler C2346

"Function" kann nicht als System eigen kompiliert werden: Grund

Der Compiler war nicht in der Lage, eine Funktion in MSIL zu kompilieren.

Weitere Informationen finden Sie unter [verwaltete, nicht verwaltete](../../preprocessor/managed-unmanaged.md) und [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Entfernen Sie den Code in der Funktion, der nicht in MSIL kompiliert werden kann.

1. Kompilieren Sie das Modul nicht mit **/CLR**, oder markieren Sie die Funktion nicht als nicht verwaltet mit dem nicht verwalteten Pragma.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2346 generiert.

```cpp
// C2346.cpp
// processor: x86
// compile with: /clr
// C2346 expected
struct S
{
   S()
   {
      { __asm { nop } }
   }
   virtual __clrcall ~S() { }
};

void main()
{
   S s;
}
```
