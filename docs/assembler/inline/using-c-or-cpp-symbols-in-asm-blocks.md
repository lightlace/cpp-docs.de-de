---
title: "Verwenden von C- oder C++-Symbolen in __asm-Bl&#246;cken"
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
  - "__asm-Schlüsselwort [C++], Syntax"
  - "Symbole, In __asm-Blöcken"
  - "Visual C, Symbole in __asm-Blöcken"
  - "Visual C++, In __asm-Blöcken"
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Verwenden von C- oder C++-Symbolen in __asm-Bl&#246;cken
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Ein `__asm`\-Block kann jedes C\- oder C\+\+\-Symbol im Bereich verweisen, für den der Block erscheint.  \(C\# und C\+\+\-Symbole sind Variablennamen, Funktionsnamen und Bezeichnungen. d. h. keine symbolischen Namen der Konstanten oder `enum`\-Member sind.  Sie können C\+\+\-Memberfunktionen nicht aufrufen.\)  
  
 Einige Einschränkungen gelten für die Verwendung von C\- und C\+\+\-Symbolen to:  
  
-   Jede Assemblersprachen Anweisung kann nur ein C\- oder C\+\+\-Symbol enthalten.  Mehrere Symbole können in der gleichen Assemblyanweisung nur mit **LENGTH**, TYPE\- und **SIZE** Ausdrücke angezeigt werden.  
  
-   Die Funktionen, die in einem `__asm`\-Block verwiesen werden, müssen einen Prototyp \(\) entwickelt wurden zuvor im Programm deklariert werden.  Andernfalls kann der Compiler nicht über mehrere Funktionsnamen und die Bezeichnungen im Block `__asm` unterscheiden.  
  
-   Ein `__asm`\-Block kann keine C\# oder C\+\+\-Symbole mit derselben Schreibweise wie MASM\-reservierte Wörter verwenden \(unabhängig von Groß\- und Kleinschreibung\).  MASM\-reservierte Wörter zählen z. B. **PUSH** Befehlsnamen und Registerbezeichnungen wie SI.  
  
-   Struktur\- und Unions Tage sind nicht in `__asm` Blöcke erkannt.  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von C oder C\+\+ in \_\_asm\-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)