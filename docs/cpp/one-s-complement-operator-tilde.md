---
title: "Einerkomplementoperator: ~"
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
  - "~"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~ (Operator), Syntax"
  - "bitwise-complement-Operator"
  - "compl-Operator"
  - "Einerkomplementoperator"
  - "Tildeoperator (~) für Einerkomplement"
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Einerkomplementoperator: ~
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
~ cast-expression  
```  
  
## Hinweise  
 Der Einerkomplementoperator \(`~`\), der manchmal als "bitweiser Komplementoperator" bezeichnet wird, ergibt eine bitweise Einerkomplement seines Operanden.  Das bedeutet, dass jedes Bit, das 1 im Operanden ist, 0 im Ergebnis ist.  Umgekehrt ist jedes Bit, das 0 im Operanden ist, im Ergebnis 1.  Der Operand für den Einerkomplementoperator muss ein ganzzahliger Typ sein.  
  
## Operator\-Schlüsselwort für ~  
 Der `compl`\-Operator ist die Textentsprechung von `~`.  Es gibt zwei Möglichkeiten, auf den `compl`\-Operator in Programmen zuzugreifen: Einschließen der Headerdatei `iso646.h` oder Kompilieren mit [\/Za](../build/reference/za-ze-disable-language-extensions.md).  
  
## Beispiel  
  
```  
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 In diesem Beispiel ist der neue Wert, der `y` zugewiesen ist, das Einerkomplement des Werts ohne Vorzeichen 0xFFFF oder 0x0000.  
  
 Ganzzahlige Erweiterung wird für ganzzahlige Operanden durchgeführt, und der resultierende Typ ist der Typ, auf den der Operand erweitert wird.  Weitere Informationen zur Ausführung der Heraufstufung finden Sie unter [Ganzzahlige Erweiterungen](../misc/integral-promotions.md).  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Unäre arithmetische Operatoren](../c-language/unary-arithmetic-operators.md)