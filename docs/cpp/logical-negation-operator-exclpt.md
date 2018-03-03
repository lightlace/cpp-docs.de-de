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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f63d36fc5974241fb624dd3a2afc863142516e9b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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