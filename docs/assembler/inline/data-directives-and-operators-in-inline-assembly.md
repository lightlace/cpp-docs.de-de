---
title: "Datendirektiven und Operatoren in der Inlineassembly | Microsoft Docs"
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
  - "__asm-Schlüsselwort [C++], Verweisen auf Einschränkungen"
  - "Datendirektiven [C++]"
  - "Direktiven [C++], MASM"
  - "Inlineassembly, Datendirektiven"
  - "Inlineassembly, Operatoren"
  - "MASM (Microsoft-Makroassembler), Direktiven"
  - "MASM (Microsoft-Makroassembler), Operatoren"
  - "MASM (Microsoft-Makroassembler), Strukturen"
  - "Operatoren [MASM]"
  - "Strukturen [C++], MASM"
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Datendirektiven und Operatoren in der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Obwohl ein `__asm`\-Block und C\+\+\-Datentypen C\- oder \- Objekte verweisen kann, kann er Datenobjekte mit MASM\-Direktiven oder \- Operatoren definieren.  Insbesondere können Sie die Direktiven, **DB**Definitions `DW`, **dd**, `DQ`, `DT`und `DF`oder die Operatoren `DUP` oder **DIESES**nicht verwenden.  MASM\-Strukturen und Datensätze sind ebenfalls nicht verfügbar.  Der Inlineassembler nicht akzeptiert die Direktive `STRUC`, `RECORD`, **BREITE**oder **MASKE**.  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von Assemblysprache in \_\_asm\-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)