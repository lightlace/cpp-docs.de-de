---
title: 'Relationale Operatoren: &lt;, &gt;, &lt;=, und &gt;= | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- <
- '>'
dev_langs: C++
helpviewer_keywords:
- '> operator'
- less than operator
- relational operators [C++], syntax
- '>= operator'
- greater than or equal to operators [C++]
- greater than operators [C++]
- < operator
- less than or equal to operator
- <= operator
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28d7cf77f9bea05a9220aea3d4006f64899b84ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="relational-operators-lt-gt-lt-and-gt"></a>Relationale Operatoren: &lt;, &gt;, &lt;=, und&gt;=
## <a name="syntax"></a>Syntax  
  
```  
expression < expression  
expression > expression  
expression <= expression  
expression >= expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Die binären relationalen Operatoren bestimmen die folgenden Beziehungen:  
  
-   Kleiner als (**\<**)  
  
-   Größer als (**>**)  
  
-   Kleiner als oder gleich (**\<=**)  
  
-   Größer als oder gleich (**>=**)  
  
 Die relationalen Operatoren haben Assoziativität von links nach rechts. Beide Operanden aus relationalen Operatoren müssen vom arithmetischen oder vom Zeigertyp sein. Sie ergeben Werte des `bool`-Typs. Der zurückgegebene Wert ist **"false"** (0), wenn die Beziehung im Ausdruck, andernfalls "false ist", der zurückgegebene Wert ist **"true"** (1).  
  
## <a name="example"></a>Beispiel  
  
```  
// expre_Relational_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << "The true expression 3 > 2 yields: "  
         << (3 > 2) << endl  
         << "The false expression 20 < 10 yields: "  
         << (20 < 10) << endl;  
}  
```  
  
 Die Ausdrücke im vorangehenden Beispiel müssen in Klammern eingeschlossen werden, da der Operator zum Einfügen von Streams (**<<**) hat Vorrang vor den relationalen Operatoren. Daher würde der erste Ausdruck ohne Klammern wie folgt ausgewertet:  
  
```  
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");  
```  
  
 Die üblichen arithmetischen Konvertierungen finden Sie im [Standardkonvertierungen](standard-conversions.md) werden auf die Operanden arithmetischen Typs angewendet.  
  
## <a name="comparing-pointers"></a>Vergleichen von Zeigern  
 Wenn zwei Zeiger auf Objekte vom gleichen Typs verglichen werden, wird das Ergebnis nach der Position der Objekte bestimmt, auf die im Adressbereich des Programms gezeigt wird. Zeiger können auch mit einem konstanten Ausdruck verglichen werden, der auf 0 oder einen Zeiger vom Typ void * auswertet. Wenn ein Zeiger ein Zeiger vom Typ "void" verglichen wird \*, der andere Zeiger wird implizit konvertiert, um den Typ "void" \*. Anschließend wird verglichen.  
  
 Zwei Zeiger verschiedener Typen können nicht verglichen werden, es sei denn:  
  
-   Ein Typ ist ein Klassentyp, der vom anderen Typ abgeleitet wird.  
  
-   Mindestens einer der Zeiger wird explizit in den Typ void * konvertiert (umgewandelt). (Der andere Zeiger wird implizit konvertiert, um den Typ "void" \* für die Konvertierung.)  
  
 Zwei Zeiger desselben Typs, die auf dasselbe Objekt zeigen, sind beim Vergleich garantiert gleich. Wenn zwei Zeiger auf nicht statische Member eines Objekts verglichen werden, gelten folgende Regeln:  
  
-   Wenn der Klassentyp keine Union ist und die zwei Member nicht durch getrennt sind ein *Access-Specifier*, wie öffentlich, geschützt oder privat ist, die Zeiger auf das Element deklariert zuletzt wird vergleichen größer als der Zeiger auf das Element deklariert weiter oben.  
  
-   Wenn die beiden Elemente durch getrennt sind ein *Access-Specifier*, sind die Ergebnisse nicht definiert.  
  
-   Wenn der Klassentyp eine Union ist, sind Zeiger auf unterschiedliche Datenmember in dieser Union beim Vergleich gleich.  
  
 Wenn zwei Zeiger auf Elemente desselben Arrays oder auf ein Element über das Ende des Arrays hinaus zeigen, erzielt der Zeiger auf das Objekt mit dem höheren Index einen höheren Wert. Der Vergleich von Zeigern ist nur dann garantiert gültig, wenn der Zeiger auf Objekte im gleichen Array oder auf die Position verweist, die eine Stelle nach dem Ende des Arrays liegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)   
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C-Operatoren (relational) und C-Gleichheitsoperatoren](../c-language/c-relational-and-equality-operators.md)