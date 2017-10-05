---
title: 'Bitweiser AND-Operator: &amp; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bitand
dev_langs:
- C++
helpviewer_keywords:
- AND operator
- bitwise operators, AND operator
- '& operator, bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 99ff65f38abf5cfcac135e2cc54e3df6df5f336d
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="bitwise-and-operator-amp"></a>Bitweiser AND-Operator:&amp;
## <a name="syntax"></a>Syntax  
  
```  
  
expression   
&  
 expression  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Ausdrücke können andere und-Ausdrücke sein oder (unter Berücksichtigung der Typeinschränkungen, die unten genannt werden) Gleichheitsausdrücke, relationale Ausdrücke, additive Ausdrücke, multiplikative Ausdrücke, Zeiger-zu-Member-Ausdrücke, Umwandlungsausdrücke, unäre Ausdrücke, Postfix-Ausdrücke oder primäre Ausdrücke.  
  
 Der bitweise AND-Operator (**&**) vergleicht jedes Bit des ersten Operanden mit dem entsprechenden Bit des zweiten Operanden. Wenn beide Bits 1 sind, wird das entsprechende Ergebnisbit auf 1 festgelegt. Andernfalls wird das entsprechende Ergebnisbit auf 0 (null) festgelegt.  
  
 Beide Operanden im bitweisen AND-Operator müssen vom Ganzzahltyp sein. Die üblichen arithmetischen Konvertierungen finden Sie im [Standardkonvertierungen](standard-conversions.md), auf die Operanden angewendet werden.  
  
## <a name="operator-keyword-for-"></a>Operator-Schlüsselwort für &  
 Die `bitand` Operator ist die textentsprechung von ** & **. Es gibt zwei Möglichkeiten, den Zugriff auf die `bitand` -Operator in Programmen: Fügen Sie die Headerdatei `iso646.h`, oder Kompilieren Sie mit der ["/ Za"](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [C++-Built-in-Operatoren, Rangfolge und Assoziativität](cpp-built-in-operators-precedence-and-associativity.md)  
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C-Operatoren zur Bitmanipulation](../c-language/c-bitwise-operators.md)
