---
title: 'Logischer Negationsoperator: ! | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6c8ad17195954feeeccb47896fa013302b6d7e3
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943520"
---
# <a name="logical-negation-operator-"></a>Logischer Negationsoperator: !
## <a name="syntax"></a>Syntax  
  
```  
  
! cast-expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Der logische Negationsoperator (**!**) Kehrt die Bedeutung des Operanden. Der Operand muss ein arithmetischer Typ oder Zeigertyp sein (oder ein Ausdruck, der dem arithmetischen Typ oder dem Zeigertyp gleicht). Der Operand wird implizit in den Typ konvertiert **"bool"**. Das Ergebnis ist "true", wenn der konvertierte Operand FALSE ist. Das Ergebnis ist "false", wenn der konvertierte Operand TRUE ist. Das Ergebnis ist vom Typ **"bool"**.  
  
 Für einen Ausdruck *e*, der unäre Ausdruck **! *** e* entspricht dem Ausdruck **(*** e* `==` 0), außer wenn überladene Operatoren beteiligt sind.  
  
## <a name="operator-keyword-for-"></a>Operator-Schlüsselwort für "!"  
 Die **nicht** -Operator ist die ausgeschriebene Variante von **!**. Es gibt zwei Möglichkeiten, den Zugriff auf die **nicht** -Operator in Programmen: Fügen Sie die Headerdatei `iso646.h`, oder Kompilieren Sie mit der [/Za](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).  
  
## <a name="example"></a>Beispiel  
  
```cpp 
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
 [C++-Built-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Unäre arithmetische Operatoren](../c-language/unary-arithmetic-operators.md)