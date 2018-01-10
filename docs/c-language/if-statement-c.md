---
title: if-Anweisung (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- else
- if
dev_langs: C++
helpviewer_keywords:
- if keyword [C]
- else clauses
- else keyword [C]
- if keyword [C], if statement syntax
- nested statements
ms.assetid: d7fc16a0-fdbc-4f39-b596-76e1ca4ad4a5
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb0e4929b55d6cfc0ef01ee183b74b2439b85d10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="if-statement-c"></a>if-Anweisung (C)
Die Anweisung **if** steuert den bedingten Branch. Der Text einer **if**-Anweisung wird ausgeführt, wenn der Wert des Ausdrucks ungleich 0 (null) ist. Die Syntax für die **if**-Anweisung weist zwei Formen auf.  
  
## <a name="syntax"></a>Syntax  
 *selection-statement*:  
 **if (**  *expression*  **)**  *statement*  
  
 **if (**  *expression*  **)**  *statement*  **else**  *statement*  
  
 In beiden Formen der **if**-Anweisung werden Ausdrücke ausgewertet, die über einen beliebigen Wert außer einer Struktur verfügen können, einschließlich aller Nebeneffekte.  
  
 In der ersten Form der Syntax, wenn *expression* auf „true“ (Wert ungleich 0 [null]) festgelegt ist, wird *statement* ausgeführt. Wenn *expression* „false“ ist, wird *statement* ignoriert. In der zweiten Form der Syntax, die **else** verwendet, wird das zweite *statement* ausgeführt, wenn *expression* „false“ ist. Bei beiden Formen geht die Steuerung von der **if**-Anweisung zur nächsten Anweisung im Programm, es sei denn, eine der Anweisungen enthält **break**, **continue** oder `goto`.  
  
 Nachfolgend einige Beispiele für die **if**-Anweisung:  
  
```  
if ( i > 0 )  
    y = x / i;  
else   
{  
    x = i;  
    y = f( x );  
}  
```  
  
 In diesem Beispiel wird die Anweisung `y = x/i;` ausgeführt, wenn `i` größer als 0 ist. Wenn `i` kleiner oder gleich 0 ist, wird `i` `x` und `f( x )` `y` zugewiesen. Beachten Sie, dass die Anweisung, die die **if**-Klausel bildet, mit einem Semikolon endet.  
  
 Wenn Sie **if**-Anweisungen und **else**-Klauseln schachteln, verwenden Sie geschweifte Klammern, um die Anweisungen und Klauseln in Verbundanweisungen zu gruppieren, die Ihre Absicht verdeutlichen. Wenn keine Klammern vorhanden sind, löst der Compiler Mehrdeutigkeiten auf, indem er jedes **else** dem nächstliegenden **if** zuordnet, dem ein **else** fehlt.  
  
```  
if ( i > 0 )           /* Without braces */  
    if ( j > i )  
        x = j;  
    else  
        x = i;  
```  
  
 Die Klausel **else** ist mit der inneren **if**-Anweisung in diesem Beispiel verbunden. Wenn `i` kleiner oder gleich 0 ist, wird `x` kein Wert zugewiesen.  
  
```  
if ( i > 0 )   
{                      /* With braces */  
    if ( j > i )  
        x = j;  
}  
else  
    x = i;  
```  
  
 Die geschweiften Klammern, die die innere **if**-Anweisung in diesem Beispiel umgeben, machen den **else**-Teil der Klausel der äußeren **if**-Anweisung aus. Wenn `i` kleiner oder gleich 0 ist, wird `i` `x` zugewiesen.  
  
## <a name="see-also"></a>Siehe auch  
 [if-else-Anweisung (C++)](../cpp/if-else-statement-cpp.md)