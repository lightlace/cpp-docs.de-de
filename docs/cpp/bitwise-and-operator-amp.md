---
title: "Bitweiser AND-Operator: &amp;"
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
  - "bitand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& (Operator), Bitweise Operatoren"
  - "AND-Operator"
  - "Bitweise Operatoren, AND-Operator"
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Bitweiser AND-Operator: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
expression   
&  
 expression  
  
```  
  
## Hinweise  
 Die Ausdrücke können andere und\-Ausdrücke sein oder \(unter Berücksichtigung der Typeinschränkungen, die unten genannt werden\) Gleichheitsausdrücke, relationale Ausdrücke, additive Ausdrücke, multiplikative Ausdrücke, Zeiger\-zu\-Member\-Ausdrücke, Umwandlungsausdrücke, unäre Ausdrücke, Postfix\-Ausdrücke oder primäre Ausdrücke.  
  
 Der bitweise AND\-Operator \(**&**\) vergleicht jedes Bit des ersten Operanden mit dem entsprechenden Bit des zweiten Operanden.  Wenn beide Bits 1 sind, wird das entsprechende Ergebnisbit auf 1 festgelegt.  Andernfalls wird das entsprechende Ergebnisbit auf 0 \(null\) festgelegt.  
  
 Beide Operanden im bitweisen AND\-Operator müssen vom Ganzzahltyp sein.  Die üblichen arithmetischen Konvertierungen, die in [Arithmetische Konvertierungen](../misc/arithmetic-conversions.md) abgedeckt werden, werden auf die Operanden angewendet.  
  
## Operator\-Schlüsselwort für &  
 Der `bitand`\-Operator ist die Textentsprechung von **&**.  Es gibt zwei Möglichkeiten, wie Sie in Programmen auf den `bitand`\-Operator zugreifen können: Fügen Sie die Headerdatei `iso646.h` ein, oder kompilieren Sie mit der Option [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Spracherweiterungen deaktivieren\).  
  
## Beispiel  
  
```  
// expre_Bitwise_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise AND  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0xFFFF;      // pattern 1111 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...  
}  
```  
  
## Siehe auch  
 [C\+\+\-Operatoren zur Bitmanipulation](../misc/cpp-bitwise-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C\-Operatoren zur Bitmanipulation](../c-language/c-bitwise-operators.md)