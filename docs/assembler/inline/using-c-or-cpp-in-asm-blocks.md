---
title: "Verwenden von C oder C++ in __asm-Bl&#246;cken"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm-Schlüsselwort [C++], C/C++-Elemente in"
  - "Kommentare, In __asm-Blöcken"
  - "Konstanten, In __asm-Blöcken"
  - "Inlineassembly, Mischen von Anweisungen mit C/C++-Anweisungen"
  - "Makros, __asm-Blöcke"
  - "Präprozessordirektiven"
  - "Präprozessordirektiven, Verwendet in __asm-Blöcken"
  - "Präprozessor, Direktiven"
  - "Symbole, In __asm-Blöcken"
  - "Typnamen, Verwendet in __asm-Blöcken"
  - "typedef-Namen, Verwendet in __asm-Blöcken"
ms.assetid: ae8b2b52-6b75-42e3-ac0c-ad02d922ed97
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Verwenden von C oder C++ in __asm-Bl&#246;cken
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Da inline Assemblyanweisungen mit C\# oder C\+\+\-Anweisungen kombiniert werden können, können sie C\- oder C\+\+\-Variablen über den Namen verweisen und viele andere Elemente dieser Sprachen verwenden.  
  
 Ein `__asm`\-Block kann die folgenden Sprachelemente verwenden:  
  
-   Symbole und Bezeichnungen, einschließlich Funktionsnamen und Variablen  
  
-   Konstanten, einschließlich symbolische Konstanten und `enum`\-Member  
  
-   Präprozessordirektiven Makros und  
  
-   Kommentare \( **\/\* \*\/** und **\/\/** \)  
  
-   Typnamen \(wo ein MASM\-Typ zulässig wäre\)  
  
-   `typedef` Namen in der Regel mit Operatoren wie **PTR** und TYPE oder Struktur oder Gewerkschaftsmitglieder angeben  
  
 Innerhalb eines `__asm`\-Blocks können Sie ganzzahlige Konstanten mit C\-Schreibweise oder Assembler \(Seite schreibweise 0x100 und 100h sind, z\).  Dadurch können Sie \(mit `#define`\) in C eine Konstante zu definieren und sie in C oder C\+\+ und Teile des Programms Assembly zu verwenden.  Sie können Konstanten in oktalem auch angeben, indem Sie ihnen mit 0 stehen.  0777 gibt z. B. eine oktale Konstante an.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Verwenden von Operatoren in Blöcken \_\_asm](../../assembler/inline/using-operators-in-asm-blocks.md)  
  
-   [Verwenden von C\- oder C\+\+\-Symbols in \_\_asm Blöcke](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)  
  
-   [C oder C\+\+\-Bezugspunkte \_\_asm in Blöcken zugreifen.](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)  
  
-   [Schreiben\-Funktionen mit Inlineassembly](../../assembler/inline/writing-functions-with-inline-assembly.md)  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)