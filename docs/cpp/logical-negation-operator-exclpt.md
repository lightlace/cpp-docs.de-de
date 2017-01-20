---
title: "Logischer Negationsoperator: !"
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
  - "!"
  - "Not"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! Operator"
  - "Logische Negation"
  - "NOT-Operator"
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Logischer Negationsoperator: !
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
! cast-expression  
```  
  
## Hinweise  
 Der logische Negationsoperator \(**\!**\) kehrt die Bedeutung des Operanden um.  Der Operand muss ein arithmetischer Typ oder Zeigertyp sein \(oder ein Ausdruck, der dem arithmetischen Typ oder dem Zeigertyp gleicht\).  Der Operand wird implizit in den `bool`\-Typ konvertiert.  Das Ergebnis ist **true**, wenn der konvertierte Operand **false** ist. Das Ergebnis ist **false**, wenn der konvertierte Operand **true** ist.  Das Ergebnis hat den Typ `bool`.  
  
 Für den Ausdruck *e* entspricht der unäre Ausdruck **\!***e* dem Ausdruck **\(***e* `==` 0\), außer wenn überladene Operatoren beteiligt sind.  
  
## Operator\-Schlüsselwort für "\!"  
 Der **not**\-Operator ist die Textentsprechung von **\!**.  Es gibt zwei Möglichkeiten, wie Sie in Programmen auf den Operator **not** zugreifen können: Fügen Sie die Headerdatei `iso646.h` ein, oder kompilieren Sie mit der Option [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Spracherweiterungen deaktivieren\).  
  
## Beispiel  
  
```  
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Unäre arithmetische Operatoren](../c-language/unary-arithmetic-operators.md)