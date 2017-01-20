---
title: "Relationale Operatoren: &lt;, &gt;, &lt;= und &gt;="
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "<"
  - ">"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<-Operator"
  - "<=-Operator"
  - ">-Operator"
  - ">=-Operator"
  - "Größer als-Operatoren"
  - "Größer oder gleich-Operatoren"
  - "Kleiner als-Operator"
  - "Kleiner oder gleich-Operator"
  - "Relationale Operatoren, Syntax"
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Relationale Operatoren: &lt;, &gt;, &lt;= und &gt;=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
        expression < expression  
expression > expression  
expression <= expression  
expression >= expression  
```  
  
## Hinweise  
 Die binären relationalen Operatoren bestimmen die folgenden Beziehungen:  
  
-   Kleiner als \(**\<**\)  
  
-   Größer als \(**\>**\)  
  
-   Kleiner als oder gleich \(**\<\=**\)  
  
-   Größer als oder gleich \(**\>\=**\)  
  
 Die relationalen Operatoren haben Assoziativität von links nach rechts.  Beide Operanden aus relationalen Operatoren müssen vom arithmetischen oder vom Zeigertyp sein.  Sie ergeben Werte des `bool`\-Typs.  Der zurückgegebene Wert ist **false** \(0\), wenn die Beziehung im Ausdruck falsch ist; andernfalls ist der zurückgegebene Wert **true** \(1\).  
  
## Beispiel  
  
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
  
 Die Ausdrücke im vorangehenden Beispiel müssen in Klammern gesetzt werden, denn der Operator zum Einfügen des Datenstroms \(**\<\<**\) hat Vorrang vor den relationalen Operatoren.  Daher würde der erste Ausdruck ohne Klammern wie folgt ausgewertet:  
  
```  
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");  
```  
  
 Die üblichen arithmetischen Konvertierungen, die unter [Arithmetic Conversions](../misc/arithmetic-conversions.md) beschrieben sind, werden auf die Operanden arithmetischen Typs angewendet.  
  
## Vergleichen von Zeigern  
 Wenn zwei Zeiger auf Objekte vom gleichen Typs verglichen werden, wird das Ergebnis nach der Position der Objekte bestimmt, auf die im Adressbereich des Programms gezeigt wird.  Zeiger können auch mit einem konstanten Ausdruck verglichen werden, der auf 0 oder einen Zeiger vom Typ void \* auswertet.  Wenn ein Zeiger mit einem Zeiger vom Typ void \* verglichen wird, wird der andere Zeiger implizit in den Typ void \* konvertiert.  Anschließend wird verglichen.  
  
 Zwei Zeiger verschiedener Typen können nicht verglichen werden, es sei denn:  
  
-   Ein Typ ist ein Klassentyp, der vom anderen Typ abgeleitet wird.  
  
-   Mindestens einer der Zeiger wird explizit in den Typ void \* konvertiert \(umgewandelt\).  \(Der andere Zeiger wird für die Konvertierung implizit in void \* konvertiert.\)  
  
 Zwei Zeiger desselben Typs, die auf dasselbe Objekt zeigen, sind beim Vergleich garantiert gleich.  Wenn zwei Zeiger auf nicht statische Member eines Objekts verglichen werden, gelten folgende Regeln:  
  
-   Wenn der Klassentyp keine Union ist und wenn die zwei Member nicht durch einen *access\-specifier*, wie öffentlich, geschützt oder privat, getrennt sind, erzielt der Zeiger auf den zuletzt deklarierten Member beim Vergleich einen größeren Wert als der Zeiger auf den zuvor deklarierten Member.  \(Informationen zu *access\-specifier* finden Sie im Syntaxabschnitt in [Zugriffsspezifizierer](../misc/access-specifiers.md).\)  
  
-   Wenn die zwei Member durch einen *access\-specifier* getrennt sind, sind die Ergebnisse nicht definiert.  
  
-   Wenn der Klassentyp eine Union ist, sind Zeiger auf unterschiedliche Datenmember in dieser Union beim Vergleich gleich.  
  
 Wenn zwei Zeiger auf Elemente desselben Arrays oder auf ein Element über das Ende des Arrays hinaus zeigen, erzielt der Zeiger auf das Objekt mit dem höheren Index einen höheren Wert.  Der Vergleich von Zeigern ist nur dann garantiert gültig, wenn der Zeiger auf Objekte im gleichen Array oder auf die Position verweist, die eine Stelle nach dem Ende des Arrays liegt.  
  
## Siehe auch  
 [Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C\-Operatoren \(relational\) und C\-Gleichheitsoperatoren](../c-language/c-relational-and-equality-operators.md)