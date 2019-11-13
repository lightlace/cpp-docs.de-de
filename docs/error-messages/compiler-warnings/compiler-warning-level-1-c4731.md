---
title: Compilerwarnung (Stufe 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: b2591756dfaa8887affbe4e470f1c98738b6b680
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052432"
---
# <a name="compiler-warning-level-1-c4731"></a>Compilerwarnung (Stufe 1) C4731

"Pointer": Frame Zeiger Register "Register" geändert durch Inline-Assemblycode

Ein Frame Zeiger Register wurde geändert. Sie müssen das Register in Ihrem Inlineassemblyblock oder in einer Frame Variablen (lokal oder Parameter, abhängig vom geänderten Register) speichern und wiederherstellen, oder der Code funktioniert möglicherweise nicht ordnungsgemäß.

Im folgenden Beispiel wird C4731 generiert:

```cpp
// C4731.cpp
// compile with: /W1 /LD
// processor: x86
// C4731 expected
void bad(int p) {
   __asm
   {
      mov ebp, 1
   }

   if (p == 1)
   {
      // ...
   }
}
```

EBP ist der Frame Zeiger (FPO ist nicht zulässig) und wird geändert. Wenn `p` später referenziert wird, wird relativ zu `EBP`auf Sie verwiesen. `EBP` wurde jedoch vom Code überschrieben, sodass das Programm nicht ordnungsgemäß funktioniert und möglicherweise sogar einen Fehler aufweist.