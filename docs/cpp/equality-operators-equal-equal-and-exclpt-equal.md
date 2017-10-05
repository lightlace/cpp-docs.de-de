---
title: 'Gleichheitsoperatoren: == und! = | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- not_eq
- '!='
- ==
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator, syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
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
ms.openlocfilehash: 5412869204f088e321d2a41da407026f9447eb82
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="equality-operators--and-"></a>Gleichheitsoperatoren: == und !=
## <a name="syntax"></a>Syntax  
  
```  
expression == expression  
expression != expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Die binären Gleichheitsoperatoren vergleichen die Operanden hinsichtlich strikter Gleichheit oder Ungleichheit.  
  
 Die Gleichheitsoperatoren "gleich" (`==`) und "ungleich" (`!=`) haben weniger Vorrang als die relationalen Operatoren, aber sie verhalten sich ähnlich. Der Ergebnistyp für diese Operatoren ist `bool`.  
  
 Der Ungleichheitsoperator (`==`) gibt **"true"** (1), wenn beide Operanden den gleichen Wert haben; andernfalls wird zurückgegeben **"false"** (0). Der Not-gleich-Operator (`!=`) gibt **"true"** , wenn die Operanden nicht denselben Wert haben, andernfalls wird zurückgegeben **"false"**.  
  
## <a name="operator-keyword-for-"></a>Operator-Schlüsselwort für !=  
 Der `not_eq`-Operator ist die Textentsprechung von `!=`. Es gibt zwei Möglichkeiten, den Zugriff auf die `not_eq` -Operator in Programmen: Fügen Sie die Headerdatei `iso646.h`, oder Kompilieren Sie mit der ["/ Za"](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).  
  
## <a name="example"></a>Beispiel  
  
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
  
 Gleichheitsoperatoren können Zeiger auf Member des gleichen Typs vergleichen. In einem solchen Vergleich werden Pointer-to-Member-Konvertierungen ausgeführt. Pointer-to-member können auch mit einem konstanten Ausdruck verglichen werden, der mit 0 ausgewertet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)   
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C-Operatoren (relational) und C-Gleichheitsoperatoren](../c-language/c-relational-and-equality-operators.md)
