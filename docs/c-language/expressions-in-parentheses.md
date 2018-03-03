---
title: "Ausdrücke in Klammern | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- parentheses
- expression evaluation, evaluation order
- expressions [C++], evaluating
- parentheses, expressions
ms.assetid: b8636147-6982-408c-9e64-29e40678ee43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c09209a323a06f883a54e7ecaec17c55a3bc6205
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="expressions-in-parentheses"></a>Ausdrücke in Klammern
Sie können jeden Operanden in Klammern einschließen, ohne den Typ oder den Wert des eingeschlossenen Ausdrucks zu ändern. Als Beispiel dient der folgende Ausdruck:  
  
```  
( 10 + 5 ) / 5  
```  
  
 Die Klammern um `10 + 5` bedeuten, dass der Wert von `10 + 5` zuerst ausgewertet und dann zum linken Operanden des Divisionsoperators (**/**) wird. Das Ergebnis von `( 10 + 5 ) / 5` lautet 3. Ohne die Klammern würde `10 + 5 / 5` als 11 ausgewertet werden.  
  
 Obwohl Klammern die Methode beeinflussen, wie die Operanden in einem Ausdruck gruppiert werden, können sie keine bestimmte Auswertungsreihenfolge in allen Fällen garantieren. Zum Beispiel stellen weder die Klammern noch die Gruppierung des folgenden Ausdrucks von links nach rechts den Wert von `i` in einem der Unterausdrücke sicher:  
  
```  
( i++ +1 ) * ( 2 + i )  
```  
  
 Der Compiler kann die beiden Seiten der Multiplikation in beliebiger Reihenfolge auswerten. Wenn der Anfangswert von `i` 0 (null) ist, kann der gesamte Ausdruck als eine dieser beiden Anweisungen ausgewertet werden:  
  
```  
( 0 + 1 + 1 ) * ( 2 + 1 )   
( 0 + 1 + 1 ) * ( 2 + 0 )  
```  
  
 Die Ausnahmen, die durch Nebeneffekte auftreten, werden in [Nebeneffekte](../c-language/side-effects.md) erläutert.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Ausdrücke (primär)](../c-language/c-primary-expressions.md)