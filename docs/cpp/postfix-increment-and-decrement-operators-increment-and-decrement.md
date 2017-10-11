---
title: "Inkrementierungs- und Dekrementierungsoperatoren in Präfixnotation: ++ und--| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- --
- ++
dev_langs:
- C++
helpviewer_keywords:
- increment operators [C++], syntax
- member-selection operators [C++]
- -- operator [C++], postfix decrement operators
- postfix operators [C++]
- ++ operator [C++], postfix increment operators
- decrement operators [C++], syntax
- operators [C++], postfix
- decrement operators [C++]
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b9e8939e810336150fe3d46be4c72ee1946aebcf
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="postfix-increment-and-decrement-operators--and---"></a>Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation: ++ und --
## <a name="syntax"></a>Syntax  
  
```  
postfix-expression ++  
postfix-expression --  
```  
  
## <a name="remarks"></a>Hinweise  
 C++ bietet Präfix- und Postfixinkrement- und Dekrementoperatoren. Dieser Abschnitt beschreibt nur die Postfixinkrement- und Dekrementoperatoren. (Weitere Informationen finden Sie unter [Präfixinkrement- und Dekrementoperatoren](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md).) Der Unterschied zwischen den beiden ist, dass in der Postfix-Notation der Operator nach wird *Postfix-Expression*, wohingegen in der Präfix-Notation der Operator vor wird *Ausdruck.* Das folgende Beispiel zeigt einen Postfixinkrement-Operator:  
  
```  
i++;  
```  
  
 Durch die Anwendung des Postfix-Inkrement-Operators (`++`) wird der Wert des Operanden um eine Einheit des entsprechenden Typs erhöht. Auf ähnliche Weise, die Auswirkungen der Anwendung des Postfix-Dekrementoperators (**--**) ist, dass der Wert des Operanden um eine Einheit des entsprechenden Typs verringert wird.  
  
 Es ist wichtig zu beachten, dass ein Postfixinkrement- oder dekrementausdruck ergibt den Wert des Ausdrucks **vor** Anwendung des jeweiligen Operators. Der Inkrement- oder dekrementvorgang geschieht, **nach** der Operand ausgewertet wird. Dieses Problem tritt nur auf, wenn der Postfix-Inkrement- oder Postfix-Dekrementvorgang im Kontext eines umfassenderen Ausdrucks stattfindet.  
  
 Wenn ein Postfix-Operator auf ein Funktionsargument angewendet wird, ist für den Wert des Arguments nicht gewährleistet, dass er vor der Übergabe an die Funktion inkrementiert oder dekrementiert wird.  Weitere Informationen finden Sie in Abschnitt 1.9.17 im C++-Standard.  
  
 Anwenden des Postfix-Inkrement-Operators auf einen Zeiger auf ein Array von Objekten des Typs **lange** 4 für die interne Darstellung des Zeigers tatsächlich hinzugefügt. Dieses Verhalten führt dazu, dass den Zeiger, der zuvor genannten der * n *th-Element des Arrays, zum Verweisen auf die (*n*+ 1) th-Element.  
  
 Die Operanden der Postfixinkrement- und Postfixdekrement-Operatoren muss geändert werden kann (nicht **const**) l-Werte des arithmetischen oder vom Zeigertyp-Typ. Der Typ des Ergebnisses ist dieselbe wie die *postfixausdruck*, aber es ist nicht mehr ein l-Wert.  
  
**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): der Operand eines Postfixinkrement oder Dekrement Operator möglicherweise nicht vom Typ `bool`.
  
 Der folgende Code veranschaulicht den Postfixinkrement-Operator:  
  
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
  
 Postinkrement- und Postdekrementvorgänge für Enumerationstypen werden nicht unterstützt:  
  
```  
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C - Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation](../c-language/c-postfix-increment-and-decrement-operators.md)
