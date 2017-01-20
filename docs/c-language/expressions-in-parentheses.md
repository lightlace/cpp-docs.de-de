---
title: "Ausdr&#252;cke in Klammern"
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
  - "C"
helpviewer_keywords: 
  - "Ausdrucksauswertung, Auswertungsreihenfolge"
  - "Ausdrücke [C++], Auswerten"
  - "Klammern"
  - "Klammern, Ausdrücke"
ms.assetid: b8636147-6982-408c-9e64-29e40678ee43
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Ausdr&#252;cke in Klammern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können jeden Operanden in Klammern einschließen, ohne den Typ oder den Wert des eingeschlossenen Ausdrucks zu ändern.  Als Beispiel dient der folgende Ausdruck:  
  
```  
( 10 + 5 ) / 5  
```  
  
 Die Klammern um `10 + 5` bedeuten, dass der Wert von `10 + 5` zuerst ausgewertet und dann zum linken Operanden des Divisionsoperators \(**\/**\) wird.  Das Ergebnis von `( 10 + 5 ) / 5` lautet 3.  Ohne die Klammern würde `10 + 5 / 5` als 11 ausgewertet werden.  
  
 Obwohl Klammern die Methode beeinflussen, wie die Operanden in einem Ausdruck gruppiert werden, können sie keine bestimmte Auswertungsreihenfolge in allen Fällen garantieren.  Zum Beispiel stellen weder die Klammern noch die Gruppierung des folgenden Ausdrucks von links nach rechts den Wert von `i` in einem der Unterausdrücke sicher:  
  
```  
( i++ +1 ) * ( 2 + i )  
```  
  
 Der Compiler kann die beiden Seiten der Multiplikation in beliebiger Reihenfolge auswerten.  Wenn der Anfangswert von `i` 0 \(null\) ist, kann der gesamte Ausdruck als eine dieser beiden Anweisungen ausgewertet werden:  
  
```  
( 0 + 1 + 1 ) * ( 2 + 1 )   
( 0 + 1 + 1 ) * ( 2 + 0 )  
```  
  
 Die Ausnahmen, die durch Nebeneffekte auftreten, werden in [Nebeneffekte](../c-language/side-effects.md) erläutert.  
  
## Siehe auch  
 [C\-Ausdrücke \(primär\)](../c-language/c-primary-expressions.md)