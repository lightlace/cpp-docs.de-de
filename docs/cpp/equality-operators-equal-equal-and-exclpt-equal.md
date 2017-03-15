---
title: "Gleichheitsoperatoren: == und !="
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
  - "not_eq"
  - "!="
  - "=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!=-Operator"
  - "==-Operator"
  - "Gleich-Operator"
  - "Gleichheitsoperator"
  - "Gleichheitsoperator, Syntax"
  - "Ungleich-Vergleichsoperator"
  - "not_eq-Operator"
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Gleichheitsoperatoren: == und !=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
      expression == expression  
expression != expression  
```  
  
## Hinweise  
 Die binären Gleichheitsoperatoren vergleichen die Operanden hinsichtlich strikter Gleichheit oder Ungleichheit.  
  
 Die Gleichheitsoperatoren "gleich" \(`==`\) und "ungleich" \(`!=`\) haben weniger Vorrang als die relationalen Operatoren, aber sie verhalten sich ähnlich.  Der Ergebnistyp für diese Operatoren ist `bool`.  
  
 Der Gleichheitsoperator \(`==`\) gibt **true** \(1\) zurück, wenn beide Operanden denselben Wert aufweisen; andernfalls wird **false** \(0\) zurückgegeben.  Der Ungleichheitsoperator \(`!=`\) gibt **true** zurück, wenn die Operanden nicht denselben Wert haben, sonst **false**.  
  
## Operator\-Schlüsselwort für \!\=  
 Der `not_eq`\-Operator ist die Textentsprechung von `!=`.  Es gibt zwei Möglichkeiten, wie Sie in Programmen auf den `not_eq`\-Operator zugreifen können: Fügen Sie die Headerdatei `iso646.h` ein, oder kompilieren Sie mit der Option [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Spracherweiterungen deaktivieren\).  
  
## Beispiel  
  
```  
// expre_Equality_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << boolalpha  
         << "The true expression 3 != 2 yields: "  
         << (3 != 2) << endl  
         << "The false expression 20 == 10 yields: "  
         << (20 == 10) << endl;  
}  
```  
  
 Gleichheitsoperatoren können Zeiger auf Member des gleichen Typs vergleichen.  In einem solchen Vergleich werden pointer\-to\-member\-Konvertierungen ausgeführt, wie in [Pointer\-to\-member\-Konvertierungen](../misc/pointer-to-member-conversions.md) erläutert wird.  Pointer\-to\-member können auch mit einem konstanten Ausdruck verglichen werden, der mit 0 ausgewertet wird.  
  
## Siehe auch  
 [Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C\-Operatoren \(relational\) und C\-Gleichheitsoperatoren](../c-language/c-relational-and-equality-operators.md)