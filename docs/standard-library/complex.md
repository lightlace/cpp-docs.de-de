---
title: '&lt;complex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <complex>
- std::<complex>
helpviewer_keywords:
- complex header
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
ms.openlocfilehash: 585f970f1a3482412ff225454b7acce9060e2d7c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449426"
---
# <a name="ltcomplexgt"></a>&lt;complex&gt;

Definiert die Container Vorlagen Klasse `complex` und deren unterstützende Vorlagen.

## <a name="requirements"></a>Anforderungen

**Header**: \<complex>

**Namespace:** std

## <a name="remarks"></a>Hinweise

Eine komplexe Zahl ist ein geordnetes Paar aus reellen Zahlen. Rein geometrisch ausgedrückt ist die komplexe Ebene die reelle zweidimensionale Ebene. Die speziellen Merkmale der komplexen Ebene, durch die sie sich von der reellen Ebene unterscheidet, sind darin begründet, dass sie eine zusätzliche algebraische Struktur hat. Diese algebraische Struktur hat zwei grundlegende Vorgänge:

- Addition definiert als (*a*, *b*) + (*c*, *d*) = (*a* + *c*, *b* + *d*)

- Multiplikation definiert als *(a*, *b*) \* (*c*, *d*) = *(AC* - *BD*, *AD* + *BC*)

Die Menge der komplexen Zahlen mit den Operationen für komplexe Addition und komplexe Multiplikation ist im standardmäßigen algebraischen Sinn ein Körper:

- Die Operationen Addition und Multiplikation sind kommutativ und assoziativ, und Multiplikation erfolgt vor Addition, genau so, wie dies für reelle Addition und Multiplikation für den Körper der reellen Zahlen der Fall ist.

- Die komplexe Zahl (0,0) ist die Additive Identität, und (1, 0) ist die multiplikative Identität.

- Der Additive umgekehrten Wert für eine komplexe Zahl (*a*, *b*) ist (-*a*,-*b*), und die multiplikative Umkehrung für alle komplexen Zahlen außer (0, 0) ist

   (*a*/(*a*<sup>2</sup> + *b*<sup>2</sup>), -*b*/(*a*<sup>2</sup> + *b*<sup>2</sup>))

Durch die Darstellung einer komplexen Zahl *z* = *(a*, *b*) in der Form *z* = *a* + *BI*, wobei *i*<sup>2</sup> =-1, können die Regeln für die Algebra des Satzes von reellen Zahlen auf die Satz komplexer Zahlen und ihrer Komponenten. Beispiel:

   (1 + 2*i*)  \* \* <sup></sup>    (2 + 3 i) = 1 (2 + 3 i) + 2 i (2 + 3 i) = (2 + 3 i) + (4 i + 6 i 2) = (2-6) + (3 + 4) i =-4 + 7 i \*

Das System der komplexen Zahlen ist ein Körper, jedoch kein geordneter Körper. Es gibt keine Reihenfolge der komplexen Zahlen, wie es für das Feld mit reellen Zahlen und deren Teilmengen gibt. Daher können Ungleichheiten nicht auf komplexe Zahlen angewendet werden, die sich auf reelle Zahlen befinden.

Es gibt drei allgemeine Formen der Darstellung einer komplexen Zahl *z*:

- Kartesisch: *z* = *a* + *BI*

- Polar: *z* = *r* (COS *p* + *i* Sin *p*)

- Exponentiell: *z* = *r* \* *e*<sup>*IP*</sup>

Die Ausdrücke, die in diesen Standarddarstellungen einer komplexen Zahl verwendet werden, werden wie folgt bezeichnet:

- Die reelle kartesische Komponente oder der Realteil *a*

- Die imaginäre kartesische Komponente oder der Imaginärteil *b*

- Der Modulo oder absolute Wert einer komplexen Zahl *r*.

- Der Argument-oder Phasenwinkel- *p* im Bogenmaße.

Sofern nicht anders angegeben, müssen Funktionen, die mehrere Werte zurückgeben können, einen Prinzipal Wert für ihre Argumente zurückgeben, der größer als-und kleiner oder gleich +, ist, damit Sie einen einzelnen Wert erhalten. Alle Winkel müssen in Bogenmaß ausgedrückt werden, wobei in einem Kreis 2-Bogenmaß (360 Grad) vorhanden sind.

## <a name="members"></a>Member

### <a name="functions"></a>Funktionen

|||
|-|-|
|[abs](../standard-library/complex-functions.md#abs)|Berechnet den Betrag einer komplexen Zahl.|
|[acos](../standard-library/complex-functions.md#acos)||
|[acosh](../standard-library/complex-functions.md#acosh)||
|[arg](../standard-library/complex-functions.md#arg)|Extrahiert das Argument aus einer komplexen Zahl.|
|[asin](../standard-library/complex-functions.md#asin)||
|[asinh](../standard-library/complex-functions.md#asinh)||
|[atan](../standard-library/complex-functions.md#atan)||
|[atanh](../standard-library/complex-functions.md#atanh)||
|[conj](../standard-library/complex-functions.md#conj)|Gibt die konjugierte Zahl einer komplexen Zahl zurück.|
|[cos](../standard-library/complex-functions.md#cos)|Gibt den Kosinus einer komplexen Zahl zurück.|
|[cosh](../standard-library/complex-functions.md#cosh)|Gibt den Kosinus Hyperbolicus einer komplexen Zahl zurück.|
|[exp](../standard-library/complex-functions.md#exp)|Gibt die Exponentialfunktion einer komplexen Zahl zurück.|
|[imag](../standard-library/complex-functions.md#imag)|Extrahiert die imaginäre Komponente einer komplexen Zahl.|
|[log](../standard-library/complex-functions.md#log)|Gibt den natürlichen Logarithmus einer komplexen Zahl zurück.|
|[log10](../standard-library/complex-functions.md#log10)|Gibt den Zehnerlogarithmus einer komplexen Zahl zurück.|
|[norm](../standard-library/complex-functions.md#norm)|Extrahiert die Norm einer komplexen Zahl.|
|[polar](../standard-library/complex-functions.md#polar)|Gibt die komplexe Zahl, die einem angegebenen Betrag und Argument entspricht, in kartesischer Form zurück.|
|[pow](../standard-library/complex-functions.md#pow)|Wertet die komplexe Zahl aus, die sich dadurch ergibt, dass eine Basis, die eine komplexe Zahl ist, mit einer anderen komplexen Zahl potenziert wird.|
|[proj](../standard-library/complex-functions.md#proj)||
|[real](../standard-library/complex-functions.md#real)|Extrahiert die reelle Komponente einer komplexen Zahl.|
|[sin](../standard-library/complex-functions.md#sin)|Gibt den Sinus einer komplexen Zahl zurück.|
|[sinh](../standard-library/complex-functions.md#sinh)|Gibt den Sinus Hyperbolicus einer komplexen Zahl zurück.|
|[sqrt](../standard-library/complex-functions.md#sqrt)|Gibt die Quadratwurzel einer komplexen Zahl zurück.|
|[tan](../standard-library/complex-functions.md#tan)|Gibt den Tangens einer komplexen Zahl zurück.|
|[tanh](../standard-library/complex-functions.md#tanh)|Gibt den Tangens Hyperbolicus einer komplexen Zahl zurück.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator!=](../standard-library/complex-operators.md#op_neq)|Testet zwei komplexe Zahlen auf Ungleichheit, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|
|[operator*](../standard-library/complex-operators.md#op_star)|Multipliziert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|
|[operator+](../standard-library/complex-operators.md#op_add)|Addiert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|
|[operator-](../standard-library/complex-operators.md#operator-)|Subtrahiert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|
|[operator/](../standard-library/complex-operators.md#op_div)|Dividiert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|
|[operator<\<](../standard-library/complex-operators.md#op_lt_lt)|Eine Vorlagenfunktion, die eine komplexe Zahl in den Ausgabestream einfügt.|
|[operator==](../standard-library/complex-operators.md#op_eq_eq)|Testet zwei komplexe Zahlen auf Gleichheit, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|
|[operator >>](../standard-library/complex-operators.md#op_gt_gt)|Eine Vorlagenfunktion, die einen komplexen Wert aus dem Eingabestream extrahiert.|

### <a name="classes"></a>Klassen

|||
|-|-|
|[complex\<double>](../standard-library/complex-double.md)|Die explizit spezialisierte Vorlagen Klasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ **Double**haben, wobei das erste Objekt den reellen Teil einer komplexen Zahl und das zweite den imaginären Teil darstellt.|
|[complex\<float>](../standard-library/complex-float.md)|Die explizit spezialisierte Vorlagen Klasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ **float**haben, wobei das erste Element den reellen Teil einer komplexen Zahl und das zweite den imaginären Teil darstellt.|
|[complex\<long double>](../standard-library/complex-long-double.md)|Die explizit spezialisierte Vorlagen Klasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ **long Double**haben, wobei das erste Objekt den reellen Teil einer komplexen Zahl und das zweite den imaginären Teil darstellt.|
|[complex](../standard-library/complex-class.md)|Die Vorlagenklasse beschreibt ein Objekt, mit dem das System komplexer Zahlen dargestellt wird und komplexe arithmetische Operationen ausgeführt werden.|

### <a name="literals"></a>Literale

Der Header \<complex> definiert die folgenden [benutzerdefinierten Literale](../cpp/user-defined-literals-cpp.md), mit denen eine komplexe Zahl erstellt wird, deren Realteil 0 (null) und deren Imaginärteil der Wert des Eingabeparameters ist.

|||
|-|-|
|`constexpr complex<long double> operator""il(long double d)`<br />`constexpr complex<long double> operator""il(unsigned long long d)`|Renditen`complex<long double>{0.0L, static_cast<long double>(d)}`|
|`constexpr complex<double> operator""i(long double d)`<br />`constexpr complex<double> operator""i(unsigned long long d)`|Gibt `complex<double>{0.0, static_cast<double>(d)}` zurück.|
|`constexpr complex<float> operator""if(long double d)`<br />`constexpr complex<float> operator""if(unsigned long long d)`|Gibt `complex<float>{0.0f, static_cast<float>(d)}` zurück.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
