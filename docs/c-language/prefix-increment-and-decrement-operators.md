---
title: "Inkrementierungs- und Dekrementierungsoperatoren in Pr&#228;fixnotation"
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
  - "Dekrementoperatoren"
  - "Dekrementoperatoren, Syntax"
  - "Inkrementoperatoren, Typen"
ms.assetid: 9a441bb9-d94a-4b6a-9db2-0d0d76bc480d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Inkrementierungs- und Dekrementierungsoperatoren in Pr&#228;fixnotation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die unären Operatoren \(`++` und **––**\) heißen "Präfix"\-Inkrementoperator oder \-Dekrementoperator, wenn die Inkrement\- oder Dekrementoperatoren vor dem Operanden erscheinen.  Das Postfixinkrementieren und \-dekrementieren hat Vorrang vor Präfixinkrementieren und \-dekrementieren.  Der Operand muss Ganzzahltypen, Gleitkommatypen oder Zeigertypen aufweisen und muss ein veränderlicher L\-Wert\-Ausdruck sein \(ein Ausdruck ohne das **const**\-Attribut\).  Das Ergebnis ist ein l\-value.  
  
 Wenn der Operator vor dem Operanden angegeben wird, wird der Operand inkrementiert oder dekrementiert, und der neue Wert ist das Ergebnis des Ausdrucks.  
  
 Ein Operand vom Typ "Ganzzahl" oder "Gleitkomma" wird durch den ganzzahligen Wert 1 inkrementiert oder dekrementiert.  Der Ergebnistyp entspricht dem Operandentyp.  Ein Operand vom Zeigertyp wird um die Größe des von ihm adressierten Objekts inkrementiert oder dekrementiert.  Ein inkrementierter Zeiger verweist auf das nächste Objekt. Ein dekrementierter Zeiger verweist auf das vorherige Objekt.  
  
## Beispiel  
 Dieses Beispiel veranschaulicht den unären Präfixdekrementoperator:  
  
```  
if( line[--i] != '\n' )  
    return;  
```  
  
 In diesem Beispiel wird die Variable `i` verringert, bevor sie als Index für `line` verwendet wird.  
  
## Siehe auch  
 [C\-Operatoren \(unär\)](../c-language/c-unary-operators.md)