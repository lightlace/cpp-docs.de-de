---
title: "Bitweiser exklusiver OR-Operator: ^"
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
  - "^-Operator"
  - "Bitweise Operatoren, OR-Operator"
  - "Exklusiver OR-Operator"
  - "Operatoren [C++], Bitweise"
  - "Operatoren [C++], Logisch"
  - "OR-Operator, Bitweiser exklusiver"
  - "XOR-Operator"
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Bitweiser exklusiver OR-Operator: ^
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
expression ^ expression  
```  
  
## Hinweise  
 Der bitweise exklusive OR\-Operator \(**^**\) vergleicht jedes Bit seines ersten Operanden mit dem entsprechenden Bit seines zweiten Operanden.  Wenn ein Bit 0 \(null\) und das andere Bit 1 ist, wird das entsprechende Ergebnisbit auf 1 festgelegt.  Andernfalls wird das entsprechende Ergebnisbit auf 0 \(null\) festgelegt.  
  
 Beide Operanden im bitweisen exklusiven OR\-Operator müssen vom Ganzzahltyp sein.  Die üblichen arithmetischen Konvertierungen, die in [Arithmetische Konvertierungen](../misc/arithmetic-conversions.md) abgedeckt werden, werden auf die Operanden angewendet.  
  
## Operator\-Schlüsselwort für "^"  
 Der **xor**\-Operator ist die ausgeschriebene Variante von **^**.  Es gibt zwei Möglichkeiten, wie Sie in Programmen auf den Operator **xor** zugreifen können: Fügen Sie die Headerdatei `iso646.h` ein, oder kompilieren Sie mit der Option [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Spracherweiterungen deaktivieren\).  
  
## Beispiel  
  
```  
// expre_Bitwise_Exclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise exclusive OR  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xFFFF;      // pattern 1111 ...  
  
   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...  
}  
```  
  
## Siehe auch  
 [C\+\+\-Operatoren zur Bitmanipulation](../misc/cpp-bitwise-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C\-Operatoren zur Bitmanipulation](../c-language/c-bitwise-operators.md)