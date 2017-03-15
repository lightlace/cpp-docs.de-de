---
title: "Assemblysprachenkommentare | Microsoft Docs"
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
  - "__asm-Schlüsselwort [C++], Anweisungen"
  - "Assemblysprache [C++], Kommentare"
  - "Kommentare [C++], Assemblysprache"
  - "Makros [C++], Assemblysprache"
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Assemblysprachenkommentare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 `__asm`\-Anweisungen in einem Block Assemblersprachen Kommentare können verwendet werden:  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 Da C\-Makros in eine einzige logische Zeile erweitern, vermeiden Sie unter Using Assemblersprachen Kommentare in Macros.  \(Siehe [Definieren C\-Makros als Blöcke \_\_asm](../../assembler/inline/defining-asm-blocks-as-c-macros.md)\). Ein `__asm`\-Block kann auch enthalten Kommentare im C\-Format. Weitere Informationen finden Sie unter [Verwenden von Blöcken \_\_asm in C oder C\+\+](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von Assemblysprache in \_\_asm\-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)