---
title: 'Logischer Negationsoperator: ! | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs:
- C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
caps.latest.revision: 9
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
ms.openlocfilehash: 42d6135ab442a6f158fddd4ebfec1ef669fdecfd
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="logical-negation-operator-"></a>Logischer Negationsoperator: !
## <a name="syntax"></a>Syntax  
  
```  
  
! cast-expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Der logische Negationsoperator (**!**) Kehrt die Bedeutung des Operanden. Der Operand muss ein arithmetischer Typ oder Zeigertyp sein (oder ein Ausdruck, der dem arithmetischen Typ oder dem Zeigertyp gleicht). Der Operand wird implizit in den `bool`-Typ konvertiert. Das Ergebnis ist **"true"** , wenn der konvertierte Operand **"false"**; das Ergebnis ist **"false"** , wenn der konvertierte Operand **"true"**. Das Ergebnis hat den Typ `bool`.  
  
 Für einen Ausdruck *e*, der unäre Ausdruck **!** *e* entspricht dem Ausdruck **(***e* `==` 0), es sei denn, in denen überladene Operatoren beteiligt sind.  
  
## <a name="operator-keyword-for-"></a>Operator-Schlüsselwort für "!"  
 Die **nicht** Operator ist die textentsprechung von **!**. Es gibt zwei Möglichkeiten, den Zugriff auf die **nicht** -Operator in Programmen: Fügen Sie die Headerdatei `iso646.h`, oder Kompilieren Sie mit der ["/ Za"](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit Unäroperatoren](../cpp/expressions-with-unary-operators.md)   
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Unäre arithmetische Operatoren](../c-language/unary-arithmetic-operators.md)
