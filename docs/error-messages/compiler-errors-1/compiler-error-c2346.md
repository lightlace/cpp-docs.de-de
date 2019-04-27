---
title: Compilerfehler C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: a6d75ca671e22203cb40ca18de21606834eeefa8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188090"
---
# <a name="compiler-error-c2346"></a>Compilerfehler C2346

'Funktion' kann nicht als systemeigen kompiliert werden: Grund

Der Compiler konnte nicht mit der Kompilierung einer Funktion in MSIL.

Weitere Informationen finden Sie unter [verwaltete, unverwaltete](../../preprocessor/managed-unmanaged.md) und [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Entfernen Sie den Code in der Funktion, die nicht in MSIL kompiliert werden kann.

1. Entweder sind nicht kompilieren Sie das Modul mit **"/ CLR"**, oder markieren Sie die Funktion als nicht verwaltet mit der unmanaged-Pragma.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2346 generiert.

```
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