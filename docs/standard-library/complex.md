---
title: '&lt;complex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <complex>
- std::<complex>
helpviewer_keywords:
- complex header
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
ms.openlocfilehash: e3d4330f8b0fcbce940f6647ebb8920f0b1969b6
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244681"
---
# <a name="ltcomplexgt"></a>&lt;complex&gt;

Definiert die containervorlagenklasse `complex` und deren unterstützende Vorlagen.

## <a name="requirements"></a>Anforderungen

**Header**: \<complex>

**Namespace:** std

## <a name="remarks"></a>Hinweise

Eine komplexe Zahl ist ein geordnetes Paar aus reellen Zahlen. Rein geometrisch ausgedrückt ist die komplexe Ebene die reelle zweidimensionale Ebene. Die speziellen Merkmale der komplexen Ebene, durch die sie sich von der reellen Ebene unterscheidet, sind darin begründet, dass sie eine zusätzliche algebraische Struktur hat. Diese algebraische Struktur hat zwei grundlegende Vorgänge:

- Außerdem definiert als (*eine*, *b*) + (*c*, *d*) = (*eine* + *c* , *b* + *d*)

- Multiplikation, die als definiert (*eine*, *b*) \* (*c*, *d*) = (*Ac*  -  *bd*, *Ad* + *bc*)

Die Menge der komplexen Zahlen mit den Operationen für komplexe Addition und komplexe Multiplikation ist im standardmäßigen algebraischen Sinn ein Körper:

- Die Operationen Addition und Multiplikation sind kommutativ und assoziativ, und Multiplikation erfolgt vor Addition, genau so, wie dies für reelle Addition und Multiplikation für den Körper der reellen Zahlen der Fall ist.

- Die komplexe Zahl (0, 0) ist die Additive Identität und (1, 0) ist die multiplikative Identität.

- Die gegenzahl für eine komplexe Zahl (*eine*, *b*) ist (-*eine*, -*b*), und der Kehrwert für alle komplexe Zahlen mit Ausnahme von (0, 0) ist

   (*a*/(*a*<sup>2</sup> + *b*<sup>2</sup>), -*b*/(*a*<sup>2</sup> + *b*<sup>2</sup>))

Durch die Darstellung einer komplexen Zahl *z* = (*eine*, *b*) in der Form *z* = *eine*  +  *Bi*, wobei *ich*<sup>2</sup> =-1, die Regeln für die Algebra der Menge der reellen Zahlen auf die Menge der komplexen Zahlen und deren Komponenten angewendet werden kann. Beispiel:

   (1 + 2*ich*) \* (2 + 3*ich*) = 1 \* (2 + 3*ich*) + 2*ich* \* (2 + 3*i*) = (2 + 3*ich*) + (4*ich* + 6*ich*<sup>2</sup>) = (2 bis 6) + (3 + 4)*ich* -4 + 7 =*ich*

Das System der komplexen Zahlen ist ein Körper, jedoch kein geordneter Körper. Es gibt keine Reihenfolge der komplexen Zahlen, wie es für das Feld der reellen Zahlen und deren Teilmengen gibt, daher ungleichheiten findet auf komplexe Zahlen angewendet werden können, wie sie in reelle Zahlen sind.

Es gibt drei allgemeine Formen der Darstellung einer komplexen Zahl *z*:

- Kartesisch: *z* = *eine* + *Bi*

- Polar: *z* = *r* (cos *p* + *ich* sin *p*)

- Exponentiell: *z* = *r* \* *e*<sup>*Ip*</sup>

Die Ausdrücke, die in diesen Standarddarstellungen einer komplexen Zahl verwendet werden, werden wie folgt bezeichnet:

- Die reelle kartesische Komponente oder der Realteil *a*

- Die imaginäre kartesische Komponente oder der Imaginärteil *b*

- Der Betrag oder Absolute Wert einer komplexen Zahl *r*.

- Der Argument- oder Phasenwinkel *p* im Bogenmaß zurück.

Sofern nicht anders angegeben, Funktionen, die mehrere Werte zurückgeben können, sind erforderlich, um einen Hauptwert für ihre Argumente zurückgeben,-π größer und kleiner als oder gleich + π aus, um sie einwertig bleiben. Alle Winkel müssen angegeben werden, im Bogenmaß im Bereich 2π Radiant (360 Grad) vorhanden sind, im Kreis.

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
|[complex\<double>](../standard-library/complex-double.md)|Die explizit spezialisierte Vorlagenklasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten, beide vom Typ speichert **doppelte**, wobei die erste dem Realteil einer komplexen Zahl entspricht und die Sekunde, den imaginären Teil entspricht darstellt.|
|[complex\<float>](../standard-library/complex-float.md)|Die explizit spezialisierte Vorlagenklasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten, beide vom Typ speichert **"float"** , wobei die erste dem Realteil einer komplexen Zahl entspricht und die Sekunde, den imaginären Teil entspricht darstellt.|
|[complex\<long double>](../standard-library/complex-long-double.md)|Die explizit spezialisierte Vorlagenklasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten, beide vom Typ speichert **long double**, wobei die erste dem Realteil einer komplexen Zahl entspricht und die Sekunde, den imaginären Teil entspricht darstellt.|
|[complex](../standard-library/complex-class.md)|Die Vorlagenklasse beschreibt ein Objekt, mit dem das System komplexer Zahlen dargestellt wird und komplexe arithmetische Operationen ausgeführt werden.|

### <a name="literals"></a>Literale

Der Header \<complex> definiert die folgenden [benutzerdefinierten Literale](../cpp/user-defined-literals-cpp.md), mit denen eine komplexe Zahl erstellt wird, deren Realteil 0 (null) und deren Imaginärteil der Wert des Eingabeparameters ist.

|||
|-|-|
|`constexpr complex<long double> operator""il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|Gibt zurück: `complex<long double>{0.0L, static_cast<long double>(d)}`|
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|Gibt `complex<double>{0.0, static_cast<double>(d)}` zurück.|
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|Gibt `complex<float>{0.0f, static_cast<float>(d)}` zurück.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
