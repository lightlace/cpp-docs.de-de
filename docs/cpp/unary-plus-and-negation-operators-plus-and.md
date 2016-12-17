---
title: "Un&#228;rer Plus- und Negationsoperatoren: + und -"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "+"
  - "-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "--Operator"
  - "+-Operator"
  - "+-Operator, Unäre Operatoren"
  - "Negationsoperator"
  - "Unäre Operatoren, plus"
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Un&#228;rer Plus- und Negationsoperatoren: + und -
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
+ cast-expression  
```  
  
```  
  
- cast-expression  
  
```  
  
## \+\-Operator  
 Das Ergebnis des unären Plus\-Operators \(**\+**\) ist der Wert seines Operanden.  Der Operand für den unären Plus\-Operator muss ein arithmetischer Typ sein.  
  
 Ganzzahlige Erweiterung wird für ganzzahlige Operanden ausgeführt.  Der resultierende Typ ist der Typ, in den der Operand heraufgestuft wird.  Daher resultiert der Ausdruck `+ch`, in dem `ch` vom Typ `char` ist, im Typ `int`. Der Wert bleibt unverändert.  Weitere Informationen über die Durchführung der Heraufstufung erhalten Sie unter [Ganzzahlige Erweiterungen](../misc/integral-promotions.md).  
  
## \-\-Operator  
 Der unäre Negationsoperator \(**–**\) erzeugt den negativen Wert des Operanden.  Der Operand für den unären Negationsoperator muss ein arithmetischer Typ sein.  
  
 Ganzzahlige Erweiterung wird für ganzzahlige Operanden durchgeführt, und der resultierende Typ ist der Typ, auf den der Operand erweitert wird.  Weitere Informationen zur Ausführung der Heraufstufung finden Sie unter [Ganzzahlige Erweiterungen](../misc/integral-promotions.md).  
  
## Microsoft\-spezifisch  
 Eine unäre Negation von Mengen ohne Vorzeichen wird ausgeführt, indem der Wert des Operanden von 2^n subtrahiert wird, wobei n die Anzahl von Bits in einem Objekt des angegebenen vorzeichenlosen Typs ist.  \(Microsoft C\+\+ wird auf Prozessoren ausgeführt, die Zweierkomplementarithmetik verwenden.  Bei anderen Prozessoren kann der Algorithmus für Negationen abweichen.\)  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)