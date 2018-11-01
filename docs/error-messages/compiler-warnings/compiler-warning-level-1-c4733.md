---
title: Compilerwarnung (Stufe 1) C4733
ms.date: 11/04/2016
f1_keywords:
- C4733
helpviewer_keywords:
- C4733
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
ms.openlocfilehash: 0d0b0b912ef15294f9a4362a79dffd6d7eeabed8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474918"
---
# <a name="compiler-warning-level-1-c4733"></a>Compilerwarnung (Stufe 1) C4733

Inline-Asm weist "fs": 0: Handler ist nicht als sicherer Handler registriert.

Eine Funktion, durch den Wert am FS: 0, einen neuer Ausnahmehandler hinzufügen funktioniert möglicherweise nicht mit sicheren Ausnahmen, da der Handler nicht als gültiger Ausnahmehandler registriert werden kann (siehe [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)).

Um diese Warnung zu beheben, entfernen Sie die Definition FS: 0 entweder oder deaktivieren die Warnung und verwenden Sie [. SAFESEH](../../assembler/masm/dot-safeseh.md) an den sicheren ausnahmehandlern.

Im folgende Beispiel wird die C4733 generiert:

```
// C4733.cpp
// compile with: /W1 /c
// processor: x86
#include "stdlib.h"
#include "stdio.h"
void my_handler()
{
   printf("Hello from my_handler\n");
   exit(1);
}

int main()
{
   _asm {
      push    my_handler
      mov     eax, DWORD PTR fs:0
      push    eax
      mov     DWORD PTR fs:0, esp   // C4733
   }

   *(int*)0 = 0;
}
```