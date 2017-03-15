---
title: '&lt;complex&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <complex>
- std.<complex>
- std::<complex>
dev_langs:
- C++
helpviewer_keywords:
- complex header
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
caps.latest.revision: 21
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: c1753b0f4f017c6d02fc41c427285e6adae6521b
ms.lasthandoff: 02/24/2017

---
# <a name="ltcomplexgt"></a>&lt;complex&gt;
Definiert die Containervorlagenklasse „complex“ und deren unterstützende Vorlagen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <complex>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine komplexe Zahl ist ein geordnetes Paar aus reellen Zahlen. Rein geometrisch ausgedrückt ist die komplexe Ebene die reelle zweidimensionale Ebene. Die speziellen Merkmale der komplexen Ebene, durch die sie sich von der reellen Ebene unterscheidet, sind darin begründet, dass sie eine zusätzliche algebraische Struktur hat. Diese algebraische Struktur hat zwei grundlegende Vorgänge:  
  
-   Addition, die als (*a, b*) + (*c, d*) = (*a + c, b + d)* definiert ist  
  
-   Multiplikation, die als (*a, b*) \* (*c, d*) = *ac - bd, ad + bc*) definiert ist  
  
 Die Menge der komplexen Zahlen mit den Operationen für komplexe Addition und komplexe Multiplikation ist im standardmäßigen algebraischen Sinn ein Körper:  
  
-   Die Operationen Addition und Multiplikation sind kommutativ und assoziativ, und Multiplikation erfolgt vor Addition, genau so, wie dies für reelle Addition und Multiplikation für den Körper der reellen Zahlen der Fall ist.  
  
-   Die komplexe Zahl (*0, 0*) ist die additive Identität, und (*1, 0*) ist die multiplikative Identität.  
  
-   Die Gegenzahl für eine komplexe Zahl (*a, b*) ist (*- a -b*), und der Kehrwert für alle komplexen Zahlen außer (*0, 0*) ist  
  
     (*a*/(*a*<sup>2</sup> + *b*<sup>2</sup>), -*b*/(*a*<sup>2</sup> + *b*<sup>2</sup>)  
  
 Indem eine komplexe Zahl *z = (a, b)* in der Form*z = a + bi* dargestellt wird, wobei *i*<sup>2</sup> *=* -1 ist, können die algebraischen Regeln für die Menge der reellen Zahlen auf die Menge der komplexen Zahlen und deren Komponenten angewendet werden. Beispiel:  
  
 (1 + 2*i*) \* (2 + 3*i*)    = 1\*(2 + 3*i*) + 2*i*\*(2 + 3*i*) = (2 + 3*i*) + (4*i* + 6*i*<sup>2</sup>)  
  
 = (2 –6) + (3 + 4)*i* = -4 + 7*i*  
  
 Das System der komplexen Zahlen ist ein Körper, jedoch kein geordneter Körper. Es gibt keine Reihenfolge der komplexen Zahlen, wie es sie für den Körper oder die reellen Zahlen und deren Teilmengen gibt. Daher können Ungleichheiten nicht auf komplexe Zahlen angewendet werden, wie sie auf reelle Zahlen angewendet werden, die ein geordneter Körper sind.  
  
 Es gibt drei allgemeine Formen der Darstellung einer komplexen Zahl *z*:  
  
-   Kartesisch: *z = a + bi*  
  
-   Polarform: *z = r* (cos *+ i*sin)  
  
-   Exponentiell: *z = r \** exp()  
  
 Die Ausdrücke, die in diesen Standarddarstellungen einer komplexen Zahl verwendet werden, werden wie folgt bezeichnet:  
  
-   Die reelle kartesische Komponente oder der Realteil *a*  
  
-   Die imaginäre kartesische Komponente oder der Imaginärteil *b*  
  
-   Der Betrag oder absolute Wert einer komplexen Zahl P  
  
-   Der Argument- oder Phasenwinkel.  
  
 Sofern nicht anders angegeben, müssen Funktionen, die mehrere Werte zurückgeben können, einen Hauptwert für ihre Argumente zurückgeben, der größer als -pi und kleiner gleich +pi ist, damit sie einwertig bleiben. Alle Winkel müssen in Radiant angegeben werden, wobei ein Kreis 2 pi Radiant (360 Grad) umfasst.  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[abs](../standard-library/complex-functions.md#abs)|Berechnet den Betrag einer komplexen Zahl.|  
|[arg](../standard-library/complex-functions.md#arg)|Extrahiert das Argument aus einer komplexen Zahl.|  
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
|[Real](../standard-library/complex-functions.md#real)|Extrahiert die reelle Komponente einer komplexen Zahl.|  
|[sin](../standard-library/complex-functions.md#sin)|Gibt den Sinus einer komplexen Zahl zurück.|  
|[sinh](../standard-library/complex-functions.md#sinh)|Gibt den Sinus Hyperbolicus einer komplexen Zahl zurück.|  
|[sqrt](../standard-library/complex-functions.md#sqrt)|Gibt die Quadratwurzel einer komplexen Zahl zurück.|  
|[tan](../standard-library/complex-functions.md#tan)|Gibt den Tangens einer komplexen Zahl zurück.|  
|[tanh](../standard-library/complex-functions.md#tanh)|Gibt den Tangens Hyperbolicus einer komplexen Zahl zurück.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator!=](../standard-library/complex-operators.md#operator_neq)|Testet zwei komplexe Zahlen auf Ungleichheit, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[operator*](../standard-library/complex-operators.md#operator_star)|Multipliziert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[operator+](../standard-library/complex-operators.md#operator_add)|Addiert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[operator-](../standard-library/complex-operators.md#operator-)|Subtrahiert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[operator/](../standard-library/complex-operators.md#operator_)|Dividiert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[operator<\<](../standard-library/complex-operators.md#operator_lt__lt_)|Eine Vorlagenfunktion, die eine komplexe Zahl in den Ausgabestream einfügt.|  
|[operator==](../standard-library/complex-operators.md#operator_eq_eq)|Testet zwei komplexe Zahlen auf Gleichheit, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[operator >>](../standard-library/complex-operators.md#operator_gt__gt_)|Eine Vorlagenfunktion, die einen komplexen Wert aus dem Eingabestream extrahiert.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[complex\<double>](../standard-library/complex-double.md)|Die explizit spezialisierte Vorlagenklasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ **double** haben*,* wobei das erste Objekt dem Realteil einer komplexen Zahl und das zweite Objekt dem Imaginärteil entspricht.|  
|[complex\<float>](../standard-library/complex-float.md)|Die explizit spezialisierte Vorlagenklasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ **float** haben*,* wobei das erste Objekt dem Realteil einer komplexen Zahl und das zweite Objekt dem Imaginärteil entspricht.|  
|[complex\<long double>](../standard-library/complex-long-double.md)|Die explizit spezialisierte Vorlagenklasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ `long double`* haben,* wobei das erste Objekt dem Realteil einer komplexen Zahl und das zweite Objekt dem Imaginärteil entspricht.|  
|[complex](../standard-library/complex-class.md)|Die Vorlagenklasse beschreibt ein Objekt, mit dem das System komplexer Zahlen dargestellt wird und komplexe arithmetische Operationen ausgeführt werden.|  
  
### <a name="literals"></a>Literale  
 Der Header \<complex> definiert die folgenden [benutzerdefinierten Literale](../cpp/user-defined-literals-cpp.md), mit denen eine komplexe Zahl erstellt wird, deren Realteil&0; (null) und deren Imaginärteil der Wert des Eingabeparameters ist.  
  
|||  
|-|-|  
|`constexpr complex<long double> operator""il(long double d)il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|Gibt `complex<long double>{0.0L, static_cast<long double>(d)}` zurück.|  
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|Gibt `complex<double>{0.0, static_cast<double>(d)}` zurück.|  
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|Gibt `complex<float>{0.0f, static_cast<float>(d)}` zurück.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)




