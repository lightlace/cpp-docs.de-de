---
title: "_emit Pseudoinstruction"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_emit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_emit Pseudoinstruction"
  - "Bytedefinition (Inlineassembly)"
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# _emit Pseudoinstruction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Der **\_emit** Pseudoinstruction definiert ein Byte an der aktuellen Position im aktuellen Textsegment.  Der **\_emit** Pseudoinstruction ähnelt den [DB](../../assembler/masm/db.md)\-Direktive von MASM.  
  
 Das folgende Fragment platziert die Bytes 0x4A, 0x43 und 0x4B in den Code:  
  
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
>  Wenn `_emit`\-Anweisungen, die Register und ändern, kompilieren Sie die Anwendung mit Optimierungen generiert, kann der Compiler nicht feststellen, welche Register beeinflusst werden.  Wenn `_emit` eine Anweisung generiert, die das **rax** Register ändert, weiß der Compiler nicht, dass **rax** geändert hat.  Der Compiler hat sich dann eine falsche Annahme über den Wert in diesem Register, nachdem der Inlineassemblercode ausführt.  Daher weist die Anwendung möglicherweise unvorhersehbares Verhalten auf, wenn sie ausgeführt wird.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Verwenden von Assemblysprache in \_\_asm\-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)