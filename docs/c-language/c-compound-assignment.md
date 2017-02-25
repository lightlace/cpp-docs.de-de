---
title: "C-Verbundzuweisung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zuweisungsoperatoren, Verbund"
  - "Zusammensetzungszuweisungsoperatoren"
  - "Operatoren [C], Zuweisung"
ms.assetid: db7b5893-cd56-4f1c-9981-5a024200ab63
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# C-Verbundzuweisung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Verbundzuweisungsoperatoren kombinieren den Einfachzuweisungsoperator mit einem anderen binären Operator.  Verbundzuweisungsoperatoren führen einen Vorgang aus, der vom zusätzlichen Operator angegeben wurde, und weisen das Ergebnis dann dem linken Operanden zu.  Zum Beispiel kann ein Verbundzuweisungsausdruck wie  
  
```  
  
expression1 += expression2  
```  
  
 verstanden werden als  
  
```  
  
expression1 = expression1 + expression2  
```  
  
 Allerdings ist der Verbundzuweisungsausdruck nicht mit der erweiterten Version äquivalent, da der Verbundzuweisungsausdruck *expression1* nur einmal auswertet, während die erweiterte Version *expression1* zweimal auswertet: in der Additions\- und in der Zuweisungsoperation.  
  
 Die Operanden des Verbundzuweisungsoperators müssen des Typs Ganzzahl oder Gleitkomma sein.  Jeder Verbundzuweisungsoperator führt die Konvertierungen aus, die der entsprechende binäre Operator ausführt, und schränkt die Typen seiner Operanden entsprechend ein.  Die Operatoren für die Additionszuweisung \(`+=`\) und die Subtraktionszuweisung \(**–\=**\) können über einen linken Operanden vom Zeigertyp verfügen. In diesem Fall muss der rechte Operand des Typs Ganzzahl sein.  Das Ergebnis eines Verbundzuweisungsvorgangs hat den Wert und Typ des linken Operanden.  
  
```  
#define MASK 0xff00  
  
n &= MASK;  
```  
  
 In diesem Beispiel wird ein bitweiser inklusiver AND\-Vorgang für `n` und `MASK` ausgeführt, und das Ergebnis wird `n` zugewiesen.  Die Manifestkonstante `MASK` wird mit einer [\#define](../preprocessor/hash-define-directive-c-cpp.md)\-Präprozessordirektive definiert.  
  
## Siehe auch  
 [C\-Zuweisungsoperatoren](../c-language/c-assignment-operators.md)