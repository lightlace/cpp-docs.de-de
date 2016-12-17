---
title: "C++-Ausdr&#252;cke (konstant)"
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
  - "Konstante Ausdrücke"
  - "Konstante Ausdrücke, Syntax"
  - "Ausdrücke [C++], Konstant"
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# C++-Ausdr&#252;cke (konstant)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein *konstanter* Wert verändert sich nicht.  C\+\+ bietet zwei Schlüsselwörter, mit denen Sie den Zweck eines Objekts angeben können, der nicht dazu gedacht ist, geändert zu werden, und diese Absicht erzwingen soll.  
  
 C\+\+ erfordert konstante Ausdrücke – Ausdrücke, die als Konstante ausgewertet werden – für Deklarationen von:  
  
-   Arraygrenzen  
  
-   Selektoren in case\-Anweisungen  
  
-   Bitfeldlängenangabe  
  
-   Enumerationsinitialisierer  
  
 Die einzigen Operanden, die in konstanten Ausdrücken zulässig sind, lauten:  
  
-   Literale  
  
-   Enumerationskonstanten  
  
-   Werte, die als Konstanten deklariert sind und mit konstanten Ausdrücken initialisiert werden.  
  
-   `sizeof`\-Ausdrücke  
  
 Konstanten, die keine Ganzzahlen sind, müssen \(entweder explizit oder implizit\) in ganzzahlige Typen konvertiert werden, um in einem konstanten Ausdruck zulässig zu sein.  Daher ist der folgende Code gültig:  
  
```  
const double Size = 11.0;  
char chArray[(int)Size];  
```  
  
 Explizite Konvertierungen in ganzzahlige Typen sind in konstanten Ausdrücken zulässig; alle anderen Typen und abgeleiteten Typen sind nicht zulässig, sofern sie nicht als Operanden für den `sizeof`\-Operator verwendet werden.  
  
 Der Kommaoperator sowie Zuweisungsoperatoren können nicht in konstanten Ausdrücken verwendet werden.  
  
## Siehe auch  
 [Ausdruckstypen](../cpp/types-of-expressions.md)