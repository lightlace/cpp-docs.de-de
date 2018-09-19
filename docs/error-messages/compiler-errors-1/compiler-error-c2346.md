---
title: Compilerfehler C2346 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2346
dev_langs:
- C++
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ec916bcdce1a43c597d8cfae10e5393cbeb99ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108611"
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