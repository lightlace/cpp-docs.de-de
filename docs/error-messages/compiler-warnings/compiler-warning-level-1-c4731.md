---
title: Compilerwarnung (Stufe 1) C4731 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4731
dev_langs:
- C++
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75117b34e63694cfa6aeec97abf178ff8e61a7da
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086483"
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