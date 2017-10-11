---
title: 'Address-of-Operator: &amp; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&'
dev_langs:
- C++
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 56e2606759cc381c1ae6f6f4f1f7cbc1d9d2d810
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="address-of-operator-amp"></a>Address-of-Operator:&amp;
## <a name="syntax"></a>Syntax  
  
```  
& cast-expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Unäre Address-of-Operators (**&**) nimmt die Adresse des Operanden. Bei dem Operanden des address-of-Operators kann es sich entweder um einen Funktionsbezeichner oder einen L-Wert handeln, der ein Objekt festgelegt, das kein Bitfeld ist und nicht mit dem **register**-Speicherklassenspezifizierer deklariert wurde.  
  
 Der address-of-Operator kann nur auf Variablen vom Typ „Basis“, „Struktur“, „Klasse“ oder „Union“ angewendet werden, die auf Dateibereichsebene deklariert wurden, oder auf indizierte Arrayverweise. In diesen Ausdrücken kann ein konstanter Ausdruck, der nicht den address-of-Operator einschließt, dem address-of-Ausdruck hinzugefügt oder von diesem subtrahiert werden.  
  
 Bei Anwendung auf Funktionen oder l-Werte ist das Ergebnis des Ausdrucks ein Zeigertyp (ein R-Wert), der vom Typ des Operanden abgeleitet wird. Wenn beispielsweise der Operand vom Typ `char` ist, ist das Ergebnis des Ausdrucks ein Typzeiger auf `char`. Address-of-Operators, um angewendet **const** oder `volatile` Objekte, ergibt **const** `type` ** \* ** oder `volatile` `type` ** \* **, wobei `type` ist der Typ des ursprünglichen Objekts.  
  
 Wenn die Address-of-Operator angewendet wird, um eine [qualifizierten Namen](http://msdn.microsoft.com/en-us/3fefb16d-8120-4627-8b3f-3d90fbdcd1df), das Ergebnis hängt davon ab, ob die *qualifizierten Namen* einen statischen Member angibt. Wenn dies der Fall ist, ist das Ergebnis ein Zeiger auf den Typ, der in der Deklaration des Members angegeben wird. Wenn der Member nicht statisch ist, wird das Ergebnis ist ein Zeiger auf den Member *Namen* der Klasse, indem *qualified-Class-Name*. (Siehe [Primärausdrücke](../cpp/primary-expressions.md) Weitere Informationen zu den *qualified-Class-Name*.) Das folgende Codefragment zeigt, wie sich das Ergebnis unterscheidet, abhängig davon, ob der Member statisch ist.  
  
```  
// expre_Address_Of_Operator.cpp  
// C2440 expected  
class PTM {  
public:  
           int   iValue;  
    static float fValue;  
};  
  
int main() {  
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static  
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static  
   float *spfValue     = &PTM::fValue;  // OK  
}  
```  
  
 In diesem Beispiel ergibt der Ausdruck `&PTM::fValue` den Typ `float *` anstelle von Typ `float PTM::*`, da `fValue` ein statischer Member ist.  
  
 Die Adresse einer überladenen Funktion kann nur verwendet werden, wenn klar ist, auf welche Version der Funktion verwiesen wird. Finden Sie unter [Funktionsüberladung](function-overloading.md) Informationen zum Abrufen der Adresse eines bestimmten überladenen Funktion.  
  
 Die Anwendung des address-of-Operators auf einen Referenztyp führt zum gleichen Ergebnis wie die Anwendung des Operators auf das Objekt, an das der Verweis gebunden ist. Zum Beispiel:  
  
## <a name="example"></a>Beispiel  
  
```  
// expre_Address_Of_Operator2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   double d;        // Define an object of type double.  
   double& rd = d;  // Define a reference to the object.  
  
   // Obtain and compare their addresses  
   if( &d == &rd )  
      cout << "&d equals &rd" << endl;  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
&d equals &rd  
```  
  
 Im folgenden Beispiel wird der address-of-Operator benutzt, um ein Zeigerargument an eine Funktion zu übergeben:  
  
```  
// expre_Address_Of_Operator3.cpp  
// compile with: /EHsc  
// Demonstrate address-of operator &  
  
#include <iostream>  
using namespace std;  
  
// Function argument is pointer to type int  
int square( int *n ) {  
   return (*n) * (*n);  
}  
  
int main() {  
   int mynum = 5;  
   cout << square( &mynum ) << endl;   // pass address of int  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
25  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit Unäroperatoren](../cpp/expressions-with-unary-operators.md)   
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Lvalue-Verweisdeklarator: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Dereferenzierungs- und Address-of-Operatoren](../c-language/indirection-and-address-of-operators.md)

