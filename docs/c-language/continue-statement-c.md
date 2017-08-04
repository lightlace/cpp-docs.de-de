---
title: continue-Anweisung (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- continue
dev_langs:
- C++
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: a8db43c8f6648cac30ebba0ed1cd55d425716439
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="continue-statement-c"></a>continue-Anweisung (C)
Die `continue`-Anweisung übergibt die Steuerung an die nächste Iteration der nächsten einschließenden `do`-, `for`- oder `while`-Anweisung, in der sie angezeigt wird, und umgeht alle verbleibenden Anweisungen im `do`-, `for`- oder `while`-Anweisungstext.  
  
## <a name="syntax"></a>Syntax  
 `jump-statement`:  
 `continue;`  
  
 Die nächste Iteration einer `do`-, `for`- oder `while`-Anweisungen wird wie folgt bestimmt:  
  
-   Innerhalb einer `do`-Anweisung oder einer `while`-Anweisung wird die nächste Iteration mit einer erneuten Auswertung des Ausdrucks der `do`-Anweisung oder der `while`-Anweisung begonnen.  
  
-   Eine `continue`-Anweisung in einer `for`-Anweisung führt dazu, dass der Schleifenausdruck der `for`-Anweisung ausgewertet wird. Anschließend wertet der Compiler den bedingten Ausdruck neu aus und beendet oder durchläuft den Anweisungstext je nach Ergebnis. Weitere Informationen zur [-Anweisung und den Nichtterminalen finden Sie in der ](../c-language/for-statement-c.md)for-Anweisung`for`.  
  
 In diesem Beispiel wird die `continue`-Anweisung veranschaulicht:  
  
```  
while ( i-- > 0 )   
{  
    x = f( i );  
    if ( x == 1 )  
        continue;  
    y += x * x;  
}  
```  
  
 In diesem Beispiel wird der Anweisungstext ausgeführt, während `i` größer als 0 ist. Zunächst wird `f(i)` `x` zugewiesen. Wenn `x` gleich 1 ist, wird dann die `continue`-Anweisung ausgeführt. Die übrigen Anweisungen im Text werden ignoriert, und die Ausführung wird am Anfang der Schleife mit der Auswertung des Schleifentests fortgesetzt.  
  
## <a name="see-also"></a>Siehe auch  
 [continue-Anweisung](../cpp/continue-statement-cpp.md)
