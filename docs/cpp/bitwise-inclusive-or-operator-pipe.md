---
title: 'Bitweise inklusive OR -Operator: || Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bitor
- '|'
dev_langs:
- C++
helpviewer_keywords:
- OR operator, bitwise inclusive
- bitwise operators, OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
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
ms.openlocfilehash: bb2fcc7c85e112b80929b2a8392f0e6c19ab97f2
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="bitwise-inclusive-or-operator-"></a>Bitweiser inklusiver OR-Operator: |
## <a name="syntax"></a>Syntax  
  
```  
  
expression   
|  
 expression  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Im bitweisen inklusiven OR-Operator (**&#124;**) vergleicht jedes Bit seines ersten Operanden mit dem entsprechenden Bit seines zweiten Operanden. Wenn jedes Bit 1 ist, wird das entsprechende Ergebnisbit auf 1 festgelegt. Andernfalls wird das entsprechende Ergebnisbit auf 0 (null) festgelegt.  
  
 Beide Operanden im bitweisen inklusiven OR-Operator müssen vom Ganzzahltyp sein. Die üblichen arithmetischen Konvertierungen finden Sie im [Standardkonvertierungen](standard-conversions.md) auf die Operanden angewendet werden.  
  
## <a name="operator-keyword-for-124"></a>Operator-Schlüsselwort für &#124;  
 Die `bitor` Operator ist die textentsprechung von **&#124;**. Es gibt zwei Möglichkeiten, den Zugriff auf die `bitor` -Operator in Programmen: Fügen Sie die Headerdatei `iso646.h`, oder Kompilieren Sie mit der ["/ Za"](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C-Operatoren zur Bitmanipulation](../c-language/c-bitwise-operators.md)


