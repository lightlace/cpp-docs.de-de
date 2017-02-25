---
title: "Multiplikationsoperatoren und der Modulus-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "%"
  - "/"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%-Operator"
  - "*-Operator"
  - "Arithmetische Operatoren [C++], Multiplikationsoperatoren"
  - "Divisionsoperator"
  - "Divisionsoperator, Multiplikationsoperatoren"
  - "Operator Modulo, C+"
  - "Multiplikationsoperator [C++], Multiplikationsoperatoren"
  - "Multiplikationsoperatoren [C++]"
  - "Operatoren [C++], Multiplikativ"
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Multiplikationsoperatoren und der Modulus-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
expression * expression   
expression / expression   
expression % expression  
```  
  
## Hinweise  
 Die multiplikativen Operatoren sind:  
  
-   Multiplikation \(**\***\)  
  
-   Division \(**\/**\)  
  
-   Restwert \(Rest aus Division\) \(`%`\)  
  
 Diese binären Operatoren weisen eine Assoziativität von links nach rechts auf.  
  
 Die Multiplikationsoperatoren akzeptieren Operanden arithmetischer Typen.  Der Moduloperator \(`%`\) verlangt, dass die Operanden ganzzahlig sind. \(Um den Rest einer Gleitkommadivision abzurufen, verwenden Sie die Laufzeitfunktion, [fmod](../c-runtime-library/reference/fmod-fmodf.md)\). Die Konvertierungen, die in [Arithmetische Konvertierungen](../misc/arithmetic-conversions.md) abgedeckt werden, werden auf die Operanden angewendet, und das Ergebnis entspricht dem konvertierten Typ.  
  
 Der Multiplikationsoperator ergibt das Ergebnis der Multiplikation des ersten Operanden mit dem zweiten.  
  
 Der Divisionsoperator ergibt das Ergebnis der Division des ersten Operanden durch den zweiten.  
  
 Der Modulo\-Operator liefert den Rest des folgenden Ausdrucks, bei dem *e1* der erste Operand und *e2* der zweite Operand ist: *e1* – \(*e1* \/ *e2*\) \* *e2*. Dabei sind beide Operanden Ganzzahltypen.  
  
 Division durch 0 \(null\) entweder in einer Division oder in einem Modulo\-Ausdruck ist nicht definiert und verursacht einen Laufzeitfehler.  Daher generieren die folgenden Begriffe nicht definierte, fehlerhafte Resultate:  
  
```  
i % 0  
f / 0.0  
```  
  
 Wenn beide Operanden in einer Multiplikation, Division einer einem Modulo\-Ausdruck dasselbe Vorzeichen haben, ist das Ergebnis positiv.  Andernfalls ist das Ergebnis negativ.  Das Ergebnis des Zeichens eines Modulvorgangs ist implementierungsdefiniert.  
  
> [!NOTE]
>  Da Konvertierungen, die von den Multiplikationsoperatoren ausgeführt werden, keine Überlauf\- oder Unterlaufbedingungen vorsehen, gehen Informationen möglicherweise verloren, wenn das Ergebnis eines Multiplikationsvorgangs nach der Konvertierung nicht im Typ der Operanden dargestellt werden kann.  
  
## Microsoft\-spezifisch  
 In Microsoft C\+\+ ist das Ergebnis eines Modulo\-Ausdrucks immer dasselbe wie das Vorzeichen des ersten Operanden.  
  
## END Microsoft\-spezifisch  
 Wenn die berechnete Division von zwei ganzen Zahlen ungenau ist und nur ein Operand negativ ist, ist das Ergebnis der Betrags \(Wert ohne Vorzeichen\) der größten Ganzzahl, die kleiner ist als der exakte Wert, den die Division ergeben würde.  Der berechnete Wert von –11 \/ 3 ist z. B. –3.666666666.  Das ganzzahlige Ergebnis der Division ist –3.  
  
 Die Beziehung zwischen den Multiplikationsoperatoren ist von der Identität \(*e1* \/ *e2*\) \* *e2* \+ *e1* % *e2* \=\= *e1* vorgegeben.  
  
## Beispiel  
 Das folgende Programm demonstriert die multiplikativen Operatoren.  Beachten Sie, dass jeder Operand von `10 / 3` explizit in Typ `float` umgewandelt werden muss, um ein Abschneiden zu vermeiden, sodass beide Operanden vom Typ `float` vor Division sind.  
  
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
  
## Siehe auch  
 [Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C\-Multiplikationsoperatoren](../c-language/c-multiplicative-operators.md)