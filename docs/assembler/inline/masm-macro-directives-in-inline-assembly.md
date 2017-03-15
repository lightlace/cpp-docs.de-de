---
title: "MASM-Makrodirektiven in der Inlineassembly | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Direktiven, Makros"
  - "Inlineassembly, Makrodirektiven"
  - "Makros, Direktiven"
  - "MASM (Microsoft-Makroassembler), Inlineassembly-Makrodirektiven"
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# MASM-Makrodirektiven in der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Der Inlineassembler ist nicht Macro Assembler.  Sie können MASM\-Makro Directive \(**MAKRO**, `REPT`, **IRC**, `IRP`und `ENDM`\) oder Makrofunktionen \(**\<\>\!**, **&**`%`und `.TYPE`\) nicht verwenden.  Ein `__asm`\-Block kann jedoch C\-Präprozessordirektive verwenden.  Weitere Informationen finden Sie unter [Verwenden von Blöcken \_\_asm in C oder C\+\+](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) .  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von Assemblysprache in \_\_asm\-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)