---
title: Multiplikationsoperatoren und der Modulus-Operator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '%'
- /
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], multiplicative
- arithmetic operators [C++], multiplicative operators
- modulus operator [C++]
- '* operator'
- division operator [C++], multiplicative operators
- '% operator'
- multiplication operator [C++], multiplicative operators
- multiplicative operators [C++]
- division operator
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
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
ms.openlocfilehash: b63a36817bb0366d21fba11c5e1e4eccbcc6951f
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="multiplicative-operators-and-the-modulus-operator"></a>Multiplikationsoperatoren und der Modulus-Operator
## <a name="syntax"></a>Syntax  
  
```  
expression * expression   
expression / expression   
expression % expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Die multiplikativen Operatoren sind:  
  
-   Multiplikation (**\***)  
  
-   Division (**/**)  
  
-   Restwert (Rest aus Division) (`%`)  
  
 Diese binären Operatoren weisen eine Assoziativität von links nach rechts auf.  
  
 Die Multiplikationsoperatoren akzeptieren Operanden arithmetischer Typen. Der Moduloperator (`%`) verlangt, dass die Operanden ganzzahlig sind. (Um den Rest einer Gleitkommadivision abzurufen, verwenden Sie die Funktion zur Laufzeit [Fmod](../c-runtime-library/reference/fmod-fmodf.md).) Die Konvertierungen finden Sie im [Standardkonvertierungen](standard-conversions.md) sind auf die Operanden angewendet, und das Ergebnis entspricht dem konvertierten Typ.  
  
 Der Multiplikationsoperator ergibt das Ergebnis der Multiplikation des ersten Operanden mit dem zweiten.  
  
 Der Divisionsoperator ergibt das Ergebnis der Division des ersten Operanden durch den zweiten.  
  
 Der Modulo-Operator liefert den Rest des folgenden Ausdrucks, in denen *e1* ist der erste Operand und *e2* ist die zweite: *e1* -(*e1*  /  *e2*) \* *e2*, dabei sind beide Operanden Ganzzahltypen.  
  
 Division durch 0 (null) entweder in einer Division oder in einem Modulo-Ausdruck ist nicht definiert und verursacht einen Laufzeitfehler. Daher generieren die folgenden Begriffe nicht definierte, fehlerhafte Resultate:  
  
```  
i % 0  
f / 0.0  
```  
  
 Wenn beide Operanden in einer Multiplikation, Division einer einem Modulo-Ausdruck dasselbe Vorzeichen haben, ist das Ergebnis positiv. Andernfalls ist das Ergebnis negativ. Das Ergebnis des Zeichens eines Modulvorgangs ist implementierungsdefiniert.  
  
> [!NOTE]
>  Da Konvertierungen, die von den Multiplikationsoperatoren ausgeführt werden, keine Überlauf- oder Unterlaufbedingungen vorsehen, gehen Informationen möglicherweise verloren, wenn das Ergebnis eines Multiplikationsvorgangs nach der Konvertierung nicht im Typ der Operanden dargestellt werden kann.  
  
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 In Microsoft C++ ist das Ergebnis eines Modulo-Ausdrucks immer dasselbe wie das Vorzeichen des ersten Operanden.  
  
**Ende Microsoft-spezifisch**  
 Wenn die berechnete Division von zwei ganzen Zahlen ungenau ist und nur ein Operand negativ ist, ist das Ergebnis der Betrags (Wert ohne Vorzeichen) der größten Ganzzahl, die kleiner ist als der exakte Wert, den die Division ergeben würde. Angenommen, der berechnete Wert des-11 / 3 ist-3.666666666. Das Ergebnis dieser ganzzahligen Division ist-3.  
  
 Die Beziehung zwischen den Multiplikationsoperatoren ist gegeben, durch die Identität (*e1* / *e2*) \* *e2*  +  *e1* % *e2* == *e1*.  
  
## <a name="example"></a>Beispiel  
 Das folgende Programm demonstriert die multiplikativen Operatoren. Beachten Sie, dass jeder Operand von `10 / 3` muss explizit in Typ umgewandelt werden `float` abgeschnitten, sodass beide Operanden vom Typ sind `float` vor Division.  
  
```  
// expre_Multiplicative_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   int x = 3, y = 6, z = 10;  
   cout  << "3 * 6 is " << x * y << endl  
         << "6 / 3 is " << y / x << endl  
         << "10 % 3 is " << z % x << endl  
         << "10 / 3 is " << (float) z / x << endl;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)   
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C-Multiplikationsoperatoren](../c-language/c-multiplicative-operators.md)
