---
title: "bool (C++)"
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
  - "bool_cpp"
  - "bool"
  - "__BOOL_DEFINED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__BOOL_DEFINED-Makro"
  - "bool-Schlüsselwort [C++]"
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# bool (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Schlüsselwort ist ein integrierter Typ.  Eine Variable dieses Typs kann die Werte [true](../cpp/true-cpp.md) und [false](../cpp/false-cpp.md) aufweisen.  Bedingte Ausdrücke weisen den Typ `bool` auf und haben daher Werte vom Typ `bool`.  Beispielsweise weist `i!=0` jetzt **true** oder **false** auf, je nach Wert von `i`.  
  
 Die Werte **true** und **false** weisen folgende Beziehung auf:  
  
```  
!false == true  
!true == false  
```  
  
 Betrachten Sie folgende Anweisung:  
  
```  
if (condexpr1) statement1;   
```  
  
 Wenn `condexpr1`**true** ist, wird `statement1` immer ausgeführt. Wenn `condexpr1` aber **false** ist, wird `statement1` niemals ausgeführt.  
  
 Wenn der Postfix\-Operator bzw. der Präfix\-Operator `++` auf eine Variable vom Typ `bool` angewendet wird, wird die Variable auf **true** festgelegt.  Der Postfix\- oder Präfix\-Operator `--` kann nicht auf eine Variable dieses Typs angewendet werden.  
  
 Der `bool`\-Typ ist an ganzzahligen Erweiterungen beteiligt.  Ein rvalue vom Typ `bool` kann in einen rvalue vom Typ `int` konvertiert werden, wobei **false** 0 \(null\) und **true** 1 wird.  Als gesonderter Typ ist `bool` an der Überladungsauflösung beteiligt.  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Grundlegende Typen](../cpp/fundamental-types-cpp.md)