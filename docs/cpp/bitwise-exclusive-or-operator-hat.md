---
title: 'Bitweiser exklusiver OR -Operator: ^ | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5cb405f2892ea344f145ae5f25716e1143cda38b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="bitwise-exclusive-or-operator-"></a>Bitweiser exklusiver OR-Operator: ^
## <a name="syntax"></a>Syntax  
  
```  
expression ^ expression  
```  
  
## <a name="remarks"></a>Hinweise  
Der bitweise exklusive OR-Operator (**^**) vergleicht jedes Bit seines ersten Operanden mit dem entsprechenden Bit seines zweiten Operanden. Wenn ein Bit 0 (null) und das andere Bit 1 ist, wird das entsprechende Ergebnisbit auf 1 festgelegt. Andernfalls wird das entsprechende Ergebnisbit auf 0 (null) festgelegt.  
  
Beide Operanden im bitweisen exklusiven OR-Operator müssen vom Ganzzahltyp sein. Die üblichen arithmetischen Konvertierungen finden Sie im [Standardkonvertierungen](standard-conversions.md) auf die Operanden angewendet werden.  
  
## <a name="operator-keyword-for-"></a>Operator-Schlüsselwort für "^"  
Die **Xor** Operator ist die textentsprechung von  **^** . Es gibt zwei Möglichkeiten, den Zugriff auf die **Xor** -Operator in Programmen: Fügen Sie die Headerdatei `iso646.h`, oder Kompilieren Sie mit der ["/ Za"](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).  
  
## <a name="example"></a>Beispiel  
  
```cpp  
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
  
## <a name="see-also"></a>Siehe auch  
 [C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   


