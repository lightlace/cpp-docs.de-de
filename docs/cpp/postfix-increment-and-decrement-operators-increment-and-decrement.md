---
title: "Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation: ++ und --"
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
  - "--"
  - "++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-- (Operator), Postfixdekrementoperatoren"
  - "++-Operator, Postfixinkrementoperatoren"
  - "Dekrementoperatoren"
  - "Dekrementoperatoren, Syntax"
  - "Inkrementoperatoren, Syntax"
  - "Memberauswahloperatoren"
  - "Operatoren [C++], Postfix"
  - "Postfixoperatoren"
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation: ++ und --
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
      postfix-expression   
      ++  
postfix-expression ––  
```  
  
## Hinweise  
 C\+\+ bietet Präfix\- und Postfixinkrement\- und Dekrementoperatoren. Dieser Abschnitt beschreibt nur die Postfixinkrement\- und Dekrementoperatoren. \(Weitere Informationen finden Sie unter [Präfixinkrement\- und Dekrementoperatoren](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)\). Der Unterscheid zwischen beiden besteht darin, dass in der Postfix\-Notation der Operator nach *postfix\-expression* angezeigt wird, wohingegen in der Präfix\-Notation der Operator vor *expression.* angezeigt wird. Das folgende Beispiel zeigt einen Postfixinkrement\-Operator:  
  
```  
i++;  
```  
  
 Durch die Anwendung des Postfix\-Inkrement\-Operators \(`++`\) wird der Wert des Operanden um eine Einheit des entsprechenden Typs erhöht.  Entsprechend wird durch das Anwenden des Postfix\-Dekrementoperators \(**––**\) der Wert des Operanden um eine Einheit des entsprechenden Typs verringert.  
  
 Beachten Sie unbedingt, dass ein Postfixinkrement\- oder Dekrementausdruck zum Wert der Ausdrucks **vor** Anwendung des jeweiligen Operators ausgewertet wird.  Der Inkrement\- oder Dekrementvorgang geschieht, **nachdem** der Operand ausgewertet wurde.  Dieses Problem tritt nur auf, wenn der Postfix\-Inkrement\- oder Postfix\-Dekrementvorgang im Kontext eines umfassenderen Ausdrucks stattfindet.  
  
 Wenn ein Postfix\-Operator auf ein Funktionsargument angewendet wird, ist für den Wert des Arguments nicht gewährleistet, dass er vor der Übergabe an die Funktion inkrementiert oder dekrementiert wird.  Weitere Informationen finden Sie in Abschnitt 1.9.17 im C\+\+\-Standard.  
  
 Durch die Anwendung des Postfixinkrement\-Operators auf einen Zeiger, der auf ein Array von Objekten des Typs **long** verweist, werden der internen Darstellung des Zeigers 4 hinzugefügt.  Dieses Verhalten führt dazu, dass der Zeiger, der zuvor auf das *n*\-te Element des Arrays verwiesen hat, nun auf das \(*n*\+1\)\-te Element verweist.  
  
 Die Operanden der Postfixinkrement\- und Postfixdekrement\-Operatoren müssen veränderbare \(nicht **Const**\) l\-Werte des arithmetischen Typs oder Zeigertyps sein.  Der Ergebnistyp entspricht dem Typ von *postfix\-expression*, aber es ist kein l\-Wert mehr.  
  
 Der Operand des Postfixinkrement\-Operators kann vom Typ `bool` sein. In diesem Fall wird der Operand ausgewertet und dann auf **true** gesetzt.  Der Operand eines Postfixdekrement\-Operators kann nicht vom Typ `bool` sein.  
  
 Der folgende Code veranschaulicht den Postfixinkrement\-Operator:  
  
```  
// expre_Postfix_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 10;  
   cout << i++ << endl;  
   cout << i << endl;  
}  
```  
  
 Postinkrement\- und Postdekrementvorgänge für Enumerationstypen werden nicht unterstützt:  
  
```  
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C \- Inkrementierungs\- und Dekrementierungsoperatoren in Postfixnotation](../c-language/c-postfix-increment-and-decrement-operators.md)