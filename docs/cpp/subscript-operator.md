---
title: Subscript-Operator]
ms.date: 11/04/2016
f1_keywords:
- '[]'
helpviewer_keywords:
- operators [C++], subscript
- postfix operators [C++]
- '[] operator'
- subscript operator [C++], syntax
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
ms.openlocfilehash: 2d55c18d2c9faa1a704bea129f2551937e76133c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767924"
---
# <a name="subscript-operator-"></a>Subscript-Operator]

## <a name="syntax"></a>Syntax

```
postfix-expression [ expression ]
```

## <a name="remarks"></a>Hinweise

Ein postfixausdruck (der auch ein primärer Ausdruck sein kann) gefolgt von dem Indexoperator **[]**, gibt eine Arrayindizierung.

Weitere Informationen zu verwalteten Arrays in C++ / CLI finden Sie unter [Arrays](../extensions/arrays-cpp-component-extensions.md).

In der Regel durch dargestellten Wert *Postfix-Expression* ein Zeigerwert, z. B. ein Arraybezeichner, und *Ausdruck* ist ein Ganzzahlwert (einschließlich Enumerationstypen). Syntaktisch erforderlich ist allerdings nur, dass einer der Ausdrücke vom Zeigertyp und der andere Ausdruck vom Ganzzahltyp ist. Daher möglicherweise der ganzzahlige Wert in der *Postfix-Expression* Position und der Zeigerwert können in eckigen Klammern in werden die *Ausdruck* oder tiefgestellten Position. Betrachten Sie das folgende Codefragment:

```cpp
int nArray[5] = { 0, 1, 2, 3, 4 };
cout << nArray[2] << endl;            // prints "2"
cout << 2[nArray] << endl;            // prints "2"
```

Im vorherigen Beispiel ist der Ausdruck `nArray[2]` identisch mit dem Ausdruck `2[nArray]`. Der Grund dafür ist, die das Ergebnis eines Indexausdrucks `e1[e2]` , angegeben durch:

`*((e2) + (e1))`

Die Adresse, die sich ergibt, der Ausdruck ist nicht *e2* Byte der Absenderadresse *e1*. Stattdessen wird die Adresse skaliert, um das nächste Objekt im Array ergibt *e2*. Zum Beispiel:

```cpp
double aDbl[2];
```

Die Adressen der `aDb[0]` und `aDb[1]` sind 8 Bytes auseinander – die Größe eines Objekts vom Typ **doppelte**. Diese Skalierung nach Objekttyp wird von der Programmiersprache C++ automatisch ausgeführt und in [Additive Operatoren](../cpp/additive-operators-plus-and.md) , in dem Addition und Subtraktion von Operanden des Zeigertyps erläutert wird.

Ein indexierte Ausdruck kann auch mehrere Indizes haben, wie folgt:

*expression1* **[** *expression2* **] [** *expression3* **]** ...

indexierte Ausdrücke sind von links nach rechts angeordnet. Der äußerste linke indexierte Ausdruck *expression1* **[** *expression2* **]** wird zuerst ausgewertet. Die Adresse, die sich aus dem Hinzufügen von *expression1* und *expression2* ergibt, bildet einen Zeigerausdruck. Dann wird *expression3* zu diesem Zeigerausdruck hinzugefügt, um einen neuen Zeigerausdruck zu bilden. Dies geht so lange weiter, bis der letzte Subscriptausdruck hinzugefügt wurde. Der Dereferenzierungsoperator (<strong>\*</strong>) wird angewendet, nachdem der letzte Indexierte Ausdruck ausgewertet wird, es sei denn, der letzte Zeigerwert einen Arraytyp spricht.

Ausdrücke mit mehreren Indizes verweisen auf Elemente aus mehrdimensionalen Arrays. Ein mehrdimensionales Array ist ein Array, dessen Elemente Arrays sind. Beispielsweise ist das erste Element eines dreidimensionalen Arrays ein Array mit zwei Dimensionen. Im folgenden Beispiel wird ein einfaches, zweidimensionales Array aus Zeichen deklariert und initialisiert:

```cpp
// expre_Subscript_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
#define MAX_ROWS 2
#define MAX_COLS 2

int main() {
  char c[ MAX_ROWS ][ MAX_COLS ] = { { 'a', 'b' }, { 'c', 'd' } };
  for ( int i = 0; i < MAX_ROWS; i++ )
     for ( int j = 0; j < MAX_COLS; j++ )
        cout << c[ i ][ j ] << endl;
}
```

## <a name="positive-and-negative-subscripts"></a>Positive und negative Indizes

Das erste Element eines Arrays ist Element 0. Das Spektrum eine C++ Array ist, aus *Array*[0], *Array*[*Größe* - 1]. C++ unterstützt jedoch die positiven und negativen Indizes. Negative Indizes müssen innerhalb der Array-Grenzen liegen. Andernfalls sind die Ergebnisse unvorhersehbar. Der folgende Code zeigt positive und negative Arrayfeldindizes:

```cpp
#include <iostream>
using namespace std;

int main() {
    int intArray[1024];
    for (int i = 0, j = 0; i < 1024; i++)
    {
        intArray[i] = j++;
    }

    cout << intArray[512] << endl;   // 512

    cout << 257[intArray] << endl;   // 257

    int *midArray = &intArray[512];  // pointer to the middle of the array

    cout << midArray[-256] << endl;  // 256

    cout << intArray[-256] << endl;  // unpredictable, may crash
}
```

Der negative Index in der letzten Zeile kann einen Laufzeitfehler erzeugt, da er zu einer Adresse 256 zeigt **Int** Positionen niedriger im Arbeitsspeicher als der Ursprung des Arrays. Der Zeiger `midArray` wird initialisiert, in die Mitte des `intArray`; daher ist es möglich (aber gefährliche), die sowohl positive und negative Arrayindizes auf ihn zu verwenden. Array-Indexfehler generieren keine Fehler zur Kompilierzeit, führen jedoch zu unvorhersehbaren Ergebnissen.

Der Indexoperator ist kommutativ. Daher sind die Begriffe *Array*[*Index*] und *Index*[*Array*] sind garantiert gleichwertig so lange, wie der Index Operator ist nicht überladen (siehe [überladene Operatoren](../cpp/operator-overloading.md)). Die erste Form entspricht der gängigsten Codierungspraxis, aber beide funktionieren.

## <a name="see-also"></a>Siehe auch

[Postfixausdrücke](../cpp/postfix-expressions.md)<br/>
[C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Arrays](../cpp/arrays-cpp.md)<br/>
[Eindimensionale Arrays](../c-language/one-dimensional-arrays.md)<br/>
[Mehrdimensionale Arrays](../c-language/multidimensional-arrays-c.md)<br/>
