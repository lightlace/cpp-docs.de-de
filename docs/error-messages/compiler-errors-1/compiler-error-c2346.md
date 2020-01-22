---
title: Compilerfehler C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: 91f2bac38166a8972193a7aaa7e84913b941c799
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518321"
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

int main()
{
   S s;
}
```
