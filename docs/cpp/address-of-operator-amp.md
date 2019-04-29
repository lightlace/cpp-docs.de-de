---
title: 'Address-of-Operator: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
ms.openlocfilehash: a03a6100c372e059bd9ef2ddde0558da307923dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385023"
---
# <a name="address-of-operator-amp"></a>Address-of-Operator: &amp;

## <a name="syntax"></a>Syntax

```
& cast-expression
```

## <a name="remarks"></a>Hinweise

Unäre Address-of-Operators (**&**) nimmt die Adresse seines Operanden. Der Operand des Address-of-Operators kann sein, entweder einen Funktionsbezeichner oder einen l-Wert, der ein Objekt festgelegt, das kein Bitfeld ist.

Der address-of-Operator kann nur auf Variablen vom Typ "Basis", "Struktur", "Klasse" oder "Union" angewendet werden, die auf Dateibereichsebene deklariert wurden, oder auf indizierte Arrayverweise. In diesen Ausdrücken kann ein konstanter Ausdruck, der nicht den address-of-Operator einschließt, dem address-of-Ausdruck hinzugefügt oder von diesem subtrahiert werden.

Bei Anwendung auf Funktionen oder L-Werte ist das Ergebnis des Ausdrucks ein Zeigertyp (ein R-Wert), der vom Typ des Operanden abgeleitet wird. Wenn der Operand ist z. B. **Char**, das Ergebnis des Ausdrucks ist ein Zeiger auf **Char**. Der Address-of-Operator, auf angewendet **const** oder **flüchtige** -Objekte `const type *` oder `volatile type *`, wobei **Typ** ist der Typ des ursprünglichen -Objekt.

Wenn die Address-of-Operator auf ein qualifizierter Name angewendet wird, hängt das Ergebnis an, ob die *qualifizierten Namen* einen statischen Member angibt. Wenn dies der Fall ist, ist das Ergebnis ein Zeiger auf den Typ, der in der Deklaration des Members angegeben wird. Wenn der Member nicht statisch ist, wird das Ergebnis ist ein Zeiger auf die Member *Namen* der Klasse erkennbar *qualified-Class-Name*. (Finden Sie unter [Primärausdrücke](../cpp/primary-expressions.md) für Weitere Informationen zu *qualified-Class-Name*.) Das folgende Codefragment zeigt, wie sich das Ergebnis unterscheidet, abhängig davon, ob der Member statisch ist.

```cpp
// expre_Address_Of_Operator.cpp
// C2440 expected
class PTM {
public:
    int iValue;
    static float fValue;
};

int main() {
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static
   float *spfValue     = &PTM::fValue;  // OK
}
```

In diesem Beispiel ergibt der Ausdruck `&PTM::fValue` den Typ `float *` anstelle von Typ `float PTM::*`, da `fValue` ein statischer Member ist.

Die Adresse einer überladenen Funktion kann nur verwendet werden, wenn klar ist, auf welche Version der Funktion verwiesen wird. Finden Sie unter [Funktionsüberladung](function-overloading.md) Informationen zum Abrufen der Adresse einer bestimmten überladenen Funktion.

Die Anwendung des address-of-Operators auf einen Referenztyp führt zum gleichen Ergebnis wie die Anwendung des Operators auf das Objekt, an das der Verweis gebunden ist. Zum Beispiel:

## <a name="example"></a>Beispiel

```cpp
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

## <a name="output"></a>Output

```Output
&d equals &rd
```

Im folgenden Beispiel wird der address-of-Operator benutzt, um ein Zeigerargument an eine Funktion zu übergeben:

```cpp
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

## <a name="output"></a>Output

```Output
25
```

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)<br/>
[C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Lvalue-Verweisdeklarator: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Dereferenzierungs- und Address-of-Operatoren](../c-language/indirection-and-address-of-operators.md)