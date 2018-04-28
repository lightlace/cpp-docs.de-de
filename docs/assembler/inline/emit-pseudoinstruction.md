---
title: _emit Pseudoinstruction | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- _emit
dev_langs:
- C++
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ad75f4abf2e86cb08ba646e50e9390650993d05
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="emit-pseudoinstruction"></a>_emit Pseudoinstruction
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Die **_emit** Pseudoinstruction ein Byte an der aktuellen Position in der aktuellen Textsegment definiert. Die **_emit** Pseudoinstruction ähnelt der [DB](../../assembler/masm/db.md) -Direktive der MASM.  
  
 Das folgende Fragment platziert die Bytes 0x4A 0x43 und 0x4B in den Code ein:  
  
```  
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B  
 .  
 .  
 .  
__asm {  
     randasm  
     }  
```  
  
> [!CAUTION]
>  Wenn `_emit` werden Anweisungen erzeugt, die Register, ändern und kompilieren Sie die Anwendung mit aktivierten Optimierungen, das der Compiler nicht ermitteln, welche Register betroffen sind. Z. B. wenn `_emit` generiert eine Anweisung, die ändert die **Rax** registrieren, der Compiler ist nicht bekannt, die **Rax** hat sich geändert. Der Compiler kann dann, eine falsche Annahme über den Wert in diesem registrieren, nachdem die Inlineassemblercode ausgeführt wird. Daher kann die Anwendung unvorhersehbares Verhalten aufweisen, bei der Ausführung.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)