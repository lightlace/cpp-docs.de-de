---
title: Compilerwarnung (Stufe 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: af091d1d35fff955afcc5af3da48b80416e79f36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385432"
---
# <a name="compiler-warning-level-1-c4731"></a>Compilerwarnung (Stufe 1) C4731

"Zeiger": Framezeigerregister "registrieren" von Inline-Assemblycode geändert

Ein Framezeigerregister wurde geändert. Müssen Sie speichern und Wiederherstellen der Registrierung in Ihre Assembly-Block oder der Zielframe inlinevariable (lokal oder Parameter je nach der Registrierung geändert), oder der Code möglicherweise nicht ordnungsgemäß.

Im folgende Beispiel wird die C4731 generiert:

```
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

EBP ist die Frame-Pointer (FPO ist nicht zulässig), und wird geändert. Wenn `p` später auf die verwiesen wird, verweist auf relativ zum `EBP`. Aber `EBP` wurde überschrieben durch den Code, damit das Programm wird nicht ordnungsgemäß funktionieren, und möglicherweise sogar einen Fehler.