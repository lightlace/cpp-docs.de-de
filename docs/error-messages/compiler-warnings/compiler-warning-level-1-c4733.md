---
title: Compilerwarnung (Stufe 1) C4733
ms.date: 11/04/2016
f1_keywords:
- C4733
helpviewer_keywords:
- C4733
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
ms.openlocfilehash: fbecdda481748aa77eefdab8d61e50350804e09f
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051324"
---
# <a name="compiler-warning-level-1-c4733"></a>Compilerwarnung (Stufe 1) C4733

Inline-ASM weist "FS: 0" zu: der Handler ist nicht als sicherer Handler registriert.

Eine Funktion, die den Wert bei FS ändert: 0 zum Hinzufügen eines neuen Ausnahme Handlers funktioniert möglicherweise nicht mit sicheren Ausnahmen, da der Handler möglicherweise nicht als gültiger Ausnahmehandler registriert ist (siehe [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)).

Um diese Warnung zu beheben, entfernen Sie entweder den folgenden FS: 0 Definition oder deaktivieren Sie diese Warnung, und verwenden Sie [. SAFESEH](../../assembler/masm/dot-safeseh.md) zum Angeben der sicheren Ausnahmehandler.

Im folgenden Beispiel wird C4733 generiert:

```cpp
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