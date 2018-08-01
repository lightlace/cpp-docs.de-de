---
title: 'Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation: ++ und--| Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1a878fe1c18889c1abfef995786ffcc9a267981
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404053"
---
# <a name="postfix-increment-and-decrement-operators--and---"></a>Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation: ++ und --
## <a name="syntax"></a>Syntax  
  
```  
postfix-expression ++  
postfix-expression --  
```  
  
## <a name="remarks"></a>Hinweise  
 C++ bietet Präfix- und Postfixinkrement- und Dekrementoperatoren. Dieser Abschnitt beschreibt nur die Postfixinkrement- und Dekrementoperatoren. (Weitere Informationen finden Sie unter [Präfixinkrement- und Dekrementoperatoren](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md).) Der Unterschied zwischen den beiden ist, dass in der Postfix-Notation der Operator nach angezeigt *Postfix-Expression*, während Sie in der Präfix-Notation der Operator vor dem angezeigt wird *Ausdruck.* Das folgende Beispiel zeigt einen Postfixinkrement-Operator:  
  
```cpp 
i++;  
```  
  
 Der Effekt der Anwendung des Postfixinkrement-Operators (**++**) besteht darin, dass der Wert des Operanden um eine Einheit des entsprechenden Typs erhöht wird. Auf ähnliche Weise die Auswirkungen der Anwendung des Postfix-Dekrementoperators (**--**) besteht darin, dass der Wert des Operanden um eine Einheit des entsprechenden Typs verringert wird.  
  
 Es ist wichtig zu beachten, dass ein Postfixinkrement- oder dekrementausdruck ergibt den Wert des Ausdrucks *vor* Anwendung des jeweiligen Operators. Das Inkrement oder dekrementvorgang geschieht, *nach* der Operand ausgewertet. Dieses Problem tritt nur auf, wenn der Postfix-Inkrement- oder Postfix-Dekrementvorgang im Kontext eines umfassenderen Ausdrucks stattfindet.  
  
 Wenn ein Postfix-Operator auf ein Funktionsargument angewendet wird, ist für den Wert des Arguments nicht gewährleistet, dass er vor der Übergabe an die Funktion inkrementiert oder dekrementiert wird.  Weitere Informationen finden Sie in Abschnitt 1.9.17 im C++-Standard.  
  
 Anwenden des Postfixinkrement-Operators auf einen Zeiger auf ein Array von Objekten des Typs **lange** vier für die interne Darstellung des Zeigers hinzugefügt. Dieses Verhalten führt dazu, dass den Zeiger, der zuvor bezeichnet die *n*th-Element des Arrays, zum Verweisen auf die (*n*+ 1) th-Element.  
  
 Die Operanden der Postfixinkrement-und Postfixdekrement-Operatoren müssen geändert werden (nicht **const**) l-Werte des arithmetischen Typ oder Zeigertyp. Der Typ des Ergebnisses ist identisch mit der die *Postfix-Expression*, aber es ist nicht mehr ein l-Wert.  
  
**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): der Operand eines Postfixinkrement oder Dekrement Operator möglicherweise nicht vom Typ **"bool"**.
  
 Der folgende Code veranschaulicht den Postfixinkrement-Operator:  
  
```cpp 
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
  
```cpp 
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [C++-Built-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C - Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation](../c-language/c-postfix-increment-and-decrement-operators.md)