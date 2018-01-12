---
title: "Übersicht über C++-Anweisungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 62415d4dd5df14bfd2d26fdd976fe6e3c53ba95d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-c-statements"></a>Übersicht über C++-Anweisungen
C++-Anweisungen werden nacheinander ausgeführt, außer wenn diese Sequenz von einer Ausdrucksanweisung, einer Selektionsanweisung, einer Iterationsanweisung oder einer Sprunganweisung speziell geändert wird.  
  
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
  
 In den meisten Fällen ist die C++-Anweisungssyntax identisch mit dem ANSI C. Der Hauptunterschied zwischen den beiden, die in C ist, Deklarationen nur am Anfang eines Blocks zulässig. C++ fügt die *deklarationsanweisung*, die diese Einschränkung entfernt. Dadurch können Sie Variablen an einem Punkt im Programm einführen, an dem ein vorausberechneter Initialisierungswert berechnet werden kann.  
  
 Das Deklarieren von Variablen innerhalb von Blöcken ermöglicht Ihnen auch die genaue Steuerung des Gültigkeitsbereichs und der Lebensdauer dieser Variablen.  
  
 Die Anweisungsthemen beschreiben die folgenden C++-Schlüsselwörter:  
  
|||||  
|-|-|-|-|  
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|  
|[case](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[try](../cpp/try-throw-and-catch-statements-cpp.md)|  
|[catch](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|  
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||  
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||  
|[do](../cpp/do-while-statement-cpp.md)|[if](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../cpp/statements-cpp.md)