---
title: "EVEN- und ALIGN-Direktiven | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "align"
  - "EVEN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIGN-Direktive"
  - "Direktiven, MASM"
  - "EVEN-Direktive"
  - "MASM (Microsoft-Makroassembler), Direktiven"
  - "NOP (No Operation, Kein Vorgang-Anweisung)"
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# EVEN- und ALIGN-Direktiven
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Obwohl die meisten MASM\-Direktive Inlineassembler nicht unterstützt, unterstützt sie `EVEN` und **AUSRICHTEN**.  Diese Direktive setzen Anweisungen nicht ausgeführt **NOP** in den Assemblycode nach Bedarf ein, um Bezeichnungen für spezielle Grenzen ausgerichtet.  Dadurch ist es effizienter Befehlsaufsuche Prozessoren für einige Vorgänge.  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von Assemblysprache in \_\_asm\-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)