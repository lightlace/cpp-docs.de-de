---
title: "Bitweiser inklusiver OR-Operator: |"
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
  - "bitor"
  - "|"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "| (Operator)"
  - "Bitweise Operatoren, OR-Operator"
  - "Inklusiver OR-Operator"
  - "OR-Operator, Bitweiser inklusiver"
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Bitweiser inklusiver OR-Operator: |
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
expression   
|  
 expression  
  
```  
  
## Hinweise  
 Der bitweise inklusive OR\-Operator \(         **&#124;** \) vergleicht jedes Bit des ersten Operanden mit dem entsprechenden Bit des zweiten Operanden.  Wenn jedes Bit 1 ist, wird das entsprechende Ergebnisbit auf 1 festgelegt.  Andernfalls wird das entsprechende Ergebnisbit auf 0 \(null\) festgelegt.  
  
 Beide Operanden im bitweisen inklusiven OR\-Operator müssen vom Ganzzahltyp sein.  Die üblichen arithmetischen Konvertierungen, die in [Arithmetische Konvertierungen](../misc/arithmetic-conversions.md) abgedeckt werden, werden auf die Operanden angewendet.  
  
## Operator\-Schlüsselwort für &#124;  
 Der `bitor`\-Operator ist die Textentsprechung von              **&#124;** .  Es gibt zwei Möglichkeiten, wie Sie in Programmen auf den `bitor`\-Operator zugreifen können: Fügen Sie die Headerdatei `iso646.h` ein, oder kompilieren Sie mit der Option [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Spracherweiterungen deaktivieren\).  
  
## Beispiel  
  
```  
// expre_Bitwise_Inclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise inclusive OR  
#include <iostream>  
using namespace std;  
  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...  
}  
```  
  
## Siehe auch  
 [C\+\+\-Operatoren zur Bitmanipulation](../misc/cpp-bitwise-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C\-Operatoren zur Bitmanipulation](../c-language/c-bitwise-operators.md)