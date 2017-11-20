---
title: Ausdrucksanweisung (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7438899eb9c1c2f17b4e74c859d454e2b69af600
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="expression-statement-c"></a>Ausdrucksanweisung (C)
Wenn eine Ausdrucksanweisung ausgeführt wird, wird der Ausdruck nach den in [Ausdrücke und Zuweisungen](../c-language/expressions-and-assignments.md) erläuterten Regeln ausgewertet.  
  
## <a name="syntax"></a>Syntax  
 *expression-statement*:  
 *expression* opt**;**  
  
 Alle Nebeneffekte der Ausdrucksauswertung werden abgeschlossen, bevor die nächste Anweisung ausgeführt wird. Eine leere Ausdrucksanweisung wird als NULL-Anweisung bezeichnet. Weitere Informationen finden Sie unter [Die NULL-Anweisung](../c-language/null-statement-c.md).  
  
 Diese Beispiele veranschaulichen Ausdrucksanweisungen.  
  
```  
x = ( y + 3 );            /* x is assigned the value of y + 3  */  
x++;                      /* x is incremented                  */  
x = y = 0;                /* Both x and y are initialized to 0 */  
proc( arg1, arg2 );       /* Function call returning void      */  
y = z = ( f( x ) + 3 );   /* A function-call expression        */  
```  
  
 In der letzten Anweisung, dem Funktionsaufrufsausdruck, wird der Wert des Ausdrucks, der jeden beliebigen Wert, der von der Funktion zurückgegeben wird, um 3 erhöht und dann den beiden Variablen `y` und `z` zugewiesen.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../c-language/statements-c.md)