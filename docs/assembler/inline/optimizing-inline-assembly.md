---
title: "Optimieren der Inlineassembly | Microsoft Docs"
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
  - "__asm-Schlüsselwort [C++], Optimieren"
  - "Inlineassembly, Optimieren"
  - "Optimierung, Inlineassembly"
  - "Optimieren der Leistung, Inlineassembly"
  - "Speicher, Optimieren in der Inlineassembly"
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Optimieren der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Das Vorhandensein eines `__asm`\-Blocks in einer Funktion der Optimierung wirkt sich auf verschiedene Weise.  Zuerst versucht der Compiler, den `__asm`\-Block selbst zu optimieren.  Wie Sie in Assemblersprache, was genau ist, schreiben Sie abrufen.  Zweitens wirkt sich auf das Vorhandensein eines `__asm`\-Blocks Register variablen speichern.  Der Compiler kann, Variablen zu einem `__asm`\-Block enregistering, wenn der Inhalt des Registers durch den `__asm`\-Block geändert würden.  Schließlich können einige andere FUNCTION\-weite Optimierungen durch die Aufnahme der in einer Funktion Assemblersprache betroffen.  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)