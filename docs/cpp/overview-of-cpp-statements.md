---
title: "&#220;bersicht &#252;ber C++-Anweisungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anweisungen, C++"
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bersicht &#252;ber C++-Anweisungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+\-Anweisungen werden nacheinander ausgeführt, außer wenn diese Sequenz von einer Ausdrucksanweisung, einer Selektionsanweisung, einer Iterationsanweisung oder einer Sprunganweisung speziell geändert wird.  
  
 Anweisungen können folgende Typen aufweisen:  
  
```  
  
        labeled-statement  
expression-statement  
compound-statement  
selection-statement  
iteration-statement  
jump-statement  
declaration-statement  
try-throw-catch  
```  
  
 In den meisten Fällen ist die Syntax von C\+\+\-Anweisungen mit der von ANSI C identisch.  Der Hauptunterschied zwischen den beiden besteht darin, dass Deklarationen in C nur am Blockbeginn zugelassen werden, während C\+\+ die *Deklarationsanweisung* hinzufügt und somit diese Einschränkung aufhebt.  Dadurch können Sie Variablen an einem Punkt im Programm einführen, an dem ein vorausberechneter Initialisierungswert berechnet werden kann.  
  
 Das Deklarieren von Variablen innerhalb von Blöcken ermöglicht Ihnen auch die genaue Steuerung des Gültigkeitsbereichs und der Lebensdauer dieser Variablen.  
  
 Die Anweisungsthemen beschreiben die folgenden C\+\+\-Schlüsselwörter:  
  
|||||  
|-|-|-|-|  
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[\_\_if\_exists](../cpp/if-exists-statement.md)|[\_\_try](../cpp/structured-exception-handling-c-cpp.md)|  
|[case](../cpp/switch-statement-cpp.md)|[\_\_except](../cpp/structured-exception-handling-c-cpp.md)|[\_\_if\_not\_exists](../cpp/if-not-exists-statement.md)|[try](../cpp/try-throw-and-catch-statements-cpp.md)|  
|[catch](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[\_\_leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|  
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||  
|[default](../cpp/switch-statement-cpp.md)|[\_\_finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||  
|[do](../cpp/do-while-statement-cpp.md)|[if](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||  
  
## Siehe auch  
 [Anweisungen](../cpp/statements-cpp.md)