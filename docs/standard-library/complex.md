---
title: "&lt;complex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<complex>"
  - "std.<complex>"
  - "std::<complex>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complex-Header"
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# &lt;complex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die Containervorlagenklasse „complex“ und deren unterstützende Vorlagen.  
  
## Syntax  
  
```  
  
#include <complex>  
  
```  
  
## Hinweise  
 Eine komplexe Zahl ist ein geordnetes Paar aus reellen Zahlen.  Rein geometrisch ausgedrückt ist die komplexe Ebene die reelle zweidimensionale Ebene.  Die speziellen Merkmale der komplexen Ebene, durch die sie sich von der reellen Ebene unterscheidet, sind darin begründet, dass sie eine zusätzliche algebraische Struktur hat.  Diese algebraische Struktur hat zwei grundlegende Vorgänge:  
  
-   Addition, die als \(*a, b*\) \+ \(*c, d*\) \= \(*a \+ c, b \+ d*\) definiert ist  
  
-   Multiplikation, die als \(*a, b*\) \* \(*c, d*\) \= \(*ac \- bd, ad \+ bc*\) definiert ist  
  
 Die Menge der komplexen Zahlen mit den Operationen für komplexe Addition und komplexe Multiplikation ist im standardmäßigen algebraischen Sinn ein Körper:  
  
-   Die Operationen Addition und Multiplikation sind kommutativ und assoziativ, und Multiplikation erfolgt vor Addition, genau so, wie dies für reelle Addition und Multiplikation für den Körper der reellen Zahlen der Fall ist.  
  
-   Die komplexe Zahl \(*0, 0*\) ist die additive Identität, und \(*1, 0*\) ist die multiplikative Identität.  
  
-   Die Gegenzahl für eine komplexe Zahl \(*a, b*\) ist \(*\- a \-b*\), und de Kehrwert für alle komplexe Zahlen außer \(*0, 0*\) ist  
  
     \(*a*\/\(*a*<sup>2</sup> \+ *b*<sup>2</sup>\), \-*b*\/\(*a*<sup>2</sup> \+ *b*<sup>2</sup>\)  
  
 Indem eine komplexen Zahl *z \= \(a, b\)* in der Form*z \= a \+ bi* dargestellt wird, wobei *i*<sup>2</sup> *\=* \-1 ist, können die algebraischen Regeln für die Menge der reellen Zahlen auf die Menge der komplexen Zahlen und deren Komponenten angewendet werden.  Beispiel:  
  
 \(1 \+ 2*i*\) \* \(2 \+ 3*i*\)    \= 1\*\(2 \+ 3*i*\) \+ 2*i*\*\(2 \+ 3*i*\) \= \(2 \+ 3*i*\) \+ \(4*i* \+ 6*i*<sup>2</sup>\)  
  
 \= \(2 –6\) \+ \(3 \+ 4\)*i* \= \-4 \+ 7*i*  
  
 Das System der komplexen Zahlen ist ein Körper, jedoch kein geordneter Körper.  Es gibt keine Reihenfolge der komplexen Zahlen, wie es sie für den Körper oder die reellen Zahlen und deren Teilmengen gibt. Daher können Ungleichheiten nicht auf komplexe Zahlen angewendet werden, wie sie auf reelle Zahlen angewendet werden, die ein geordneter Körper sind.  
  
 Es gibt drei allgemeine Formen der Darstellung einer komplexen Zahl *z*:  
  
-   Kartesisch: *z \= a \+ bi*  
  
-   Polar: *z \= r* \(cos *\+ i*sin\)  
  
-   Exponentiell: *z \= r \** exp\(\)  
  
 Die Ausdrücke, die in diesen Standarddarstellungen einer komplexen Zahl verwendet werden, werden wie folgt bezeichnet:  
  
-   Die reelle kartesische Komponente oder der reelle Teil *a*.  
  
-   Die imaginäre kartesische Komponente oder der imaginäre Teil *b*.  
  
-   Der Betrag oder absolute Wert einer komplexen Zahl Ρ.  
  
-   Der Argument\- oder Phasenwinkel.  
  
 Sofern nicht anders angegeben, müssen Funktionen, die mehrere Werte zurückgeben können, einen Hauptwert für ihre Argumente zurückgeben, der größer als \-pi und kleiner gleich \+pi ist, damit sie einwertig bleiben.  Alle Winkel müssen in Radiant angegeben werden, wobei ein Kreis 2 pi Radiant \(360 Grad\) umfasst.  
  
### Funktionen  
  
|||  
|-|-|  
|[abs](../Topic/abs.md)|Berechnet den Betrag einer komplexen Zahl.|  
|[arg](../Topic/arg.md)|Extrahiert das Argument aus einer komplexen Zahl.|  
|[conj](../Topic/conj.md)|Gibt die konjugierte Zahl einer komplexen Zahl zurück.|  
|[cos](../Topic/cos.md)|Gibt den Kosinus einer komplexen Zahl zurück.|  
|[cosh](../Topic/cosh.md)|Gibt den Kosinus Hyperbolicus einer komplexen Zahl zurück.|  
|[exp](../Topic/exp.md)|Gibt die Exponentialfunktion einer komplexen Zahl zurück.|  
|[imag](../Topic/imag.md)|Extrahiert die imaginäre Komponente einer komplexen Zahl.|  
|[log](../Topic/log.md)|Gibt den natürlichen Logarithmus einer komplexen Zahl zurück.|  
|[log10](../Topic/log10.md)|Gibt den Zehnerlogarithmus einer komplexen Zahl zurück.|  
|[norm](../Topic/norm.md)|Extrahiert die Norm einer komplexen Zahl.|  
|[polar](../Topic/polar.md)|Gibt die komplexe Zahl, die einem angegebenen Betrag und Argument entspricht, in kartesischer Form zurück.|  
|[pow](../Topic/pow.md)|Wertet die komplexe Zahl aus, die sich dadurch ergibt, dass eine Basis, die eine komplexe Zahl ist, mit einer anderen komplexen Zahl potenziert wird.|  
|[Reelle](../Topic/real.md)|Extrahiert die reelle Komponente einer komplexen Zahl.|  
|[sin](../Topic/sin.md)|Gibt den Sinus einer komplexen Zahl zurück.|  
|[sinh](../Topic/sinh.md)|Gibt den Sinus Hyperbolicus einer komplexen Zahl zurück.|  
|[sqrt](../Topic/sqrt.md)|Gibt die Quadratwurzel einer komplexen Zahl zurück.|  
|[tan](../Topic/Functions%20tan.md)|Gibt den Tangens einer komplexen Zahl zurück.|  
|[tanh](../Topic/tanh.md)|Gibt den Tangens Hyperbolicus einer komplexen Zahl zurück.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator\!\=](../Topic/operator!=%20\(%3Ccomplex%3E\).md)|Testet zwei komplexe Zahlen auf Ungleichheit, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[operator\*](../Topic/operator*%20\(%3Ccomplex%3E\).md)|Multipliziert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[operator\+](../Topic/operator+%20\(%3Ccomplex%3E\).md)|Addiert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[operator\-](../Topic/operator-%20\(%3Ccomplex%3E\)1.md)|Subtrahiert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[operator\/](../Topic/operator-%20\(%3Ccomplex%3E\)2.md)|Dividiert zwei komplexe Zahlen, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[Operator \<\<](../Topic/operator%3C%3C%20\(%3Ccomplex%3E\).md)|Eine Vorlagenfunktion, die eine komplexe Zahl in den Ausgabestream einfügt.|  
|[operator\=\=](../Topic/operator==%20\(%3Ccomplex%3E\).md)|Testet zwei komplexe Zahlen auf Gleichheit, von denen eine oder beide einer Teilmenge des Typs für die reellen und imaginären Teile angehören.|  
|[Operator \>\>](../Topic/operator%3E%3E%20\(%3Ccomplex%3E\).md)|Eine Vorlagenfunktion, die einen komplexen Wert aus dem Eingabestream extrahiert.|  
  
### Klassen  
  
|||  
|-|-|  
|[complex\<double\>](../standard-library/complex-double.md)|Die explizit spezialisierte Vorlagenklasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ **double** haben*,* wobei das erste Objekt dem reellen Teil einer komplexen Zahl und das zweite Objekt dem imaginären Teil entspricht.|  
|[complex\<float\>](../standard-library/complex-float.md)|Die explizit spezialisierte Vorlagenklasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ **float** haben*,* wobei das erste Objekt dem reellen Teil einer komplexen Zahl und das zweite Objekt dem imaginären Teil entspricht.|  
|[complex\<long double\>](../standard-library/complex-long-double.md)|Die explizit spezialisierte Vorlagenklasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ `long double` *haben,* wobei das erste Objekt dem reellen Teil einer komplexen Zahl und das zweite Objekt dem imaginären Teil entspricht.|  
|[Komplex](../standard-library/complex-class.md)|Die Vorlagenklasse beschreibt ein Objekt, mit dem das System komplexer Zahlen dargestellt wird und komplexe arithmetische Operationen ausgeführt werden.|  
  
### Literale  
 Der Header „\<complex\>“ definiert die folgenden [benutzerdefinierten Literale](../cpp/user-defined-literals-cpp.md), mit denen eine komplexe Zahl erstellt wird, deren reeller Teil 0 \(null\) und deren imaginärer Teil der Wert des Eingabeparameters ist.  
  
|||  
|-|-|  
|`constexpr complex<long double> operator""il(long double d)il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|Gibt `complex<long double>{0.0L, static_cast<long double>(d)}` zurück.|  
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|Gibt `complex<double>{0.0, static_cast<double>(d)}` zurück.|  
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|Gibt `complex<float>{0.0f, static_cast<float>(d)}` zurück.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)