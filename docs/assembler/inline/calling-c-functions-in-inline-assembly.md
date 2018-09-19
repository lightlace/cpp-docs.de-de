---
title: Aufrufen von C-Funktionen in der Inlineassembly | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a080c05aee58a2e6ffae17d14e99c66922aa1f17
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686686"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Aufrufen von C-Funktionen in der Inlineassembly

**Microsoft-spezifisch**

Ein `__asm` Block kann die C-Funktionen, einschließlich der C-Bibliotheksroutinen aufrufen. Im folgenden Beispiel wird die `printf` Bibliotheksroutine:

```cpp
// InlineAssembler_Calling_C_Functions_in_Inline_Assembly.cpp
// processor: x86
#include <stdio.h>

char format[] = "%s %s\n";
char hello[] = "Hello";
char world[] = "world";
int main( void )
{
   __asm
   {
      mov  eax, offset world
      push eax
      mov  eax, offset hello
      push eax
      mov  eax, offset format
      push eax
      call printf
      //clean up the stack so that main can exit cleanly
      //use the unused register ebx to do the cleanup
      pop  ebx
      pop  ebx
      pop  ebx
   }
}
```

Da die Funktionsargumente auf dem Stapel übergeben werden, Sie einfach die erforderlichen Argumente übertragen – Zeigern, die im vorherigen Beispiel eine Zeichenfolge: vor dem Aufrufen der Funktion. Die Argumente werden in umgekehrter Reihenfolge abgelegt werden, damit sie vom Stapel in der gewünschten Reihenfolge eintreffen. Zum Emulieren der C-Anweisung

```cpp
printf( format, hello, world );
```

Im Beispiel legt den Zeiger auf `world`, `hello`, und `format`in dieser Reihenfolge und ruft dann `printf`.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>