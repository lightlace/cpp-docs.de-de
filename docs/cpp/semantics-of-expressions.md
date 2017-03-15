---
title: "Semantik von Ausdr&#252;cken | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausdrucksauswertung"
  - "Ausdrucksauswertung, Informationen über die Ausdrucksauswertung"
  - "Ausdrücke [C++], Semantik"
  - "Grammatik, Ausdrücke"
ms.assetid: 4a792154-533b-48b9-8709-31bfc170f0a7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Semantik von Ausdr&#252;cken
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ausdrücke werden entsprechend der Rangfolge und Gruppierung ihrer Operatoren ausgewertet.  \([Operatorrangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md) unter [Lexikalische Konventionen](../cpp/lexical-conventions.md) zeigt die Beziehungen, die die C\+\+\-Operatoren für Ausdrücke vorgeben.\)  
  
## Reihenfolge der Auswertung  
 Betrachten Sie das folgende Beispiel:  
  
```  
// expre_pluslang__pluslang_Order_of_Evaluation.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main()  
{  
    int a = 2, b = 4, c = 9;  
  
    cout << a + b * c << "\n";  
    cout << a + (b * c) << "\n";  
    cout << (a + b) * c << "\n";  
}  
//Output:  
38  
38  
54  
```  
  
 ![Auswertungsreihenfolge in einem Ausdruck](../cpp/media/vc38zv1.png "vc38ZV1")  
Reihenfolge der Auswertung von Ausdrücken  
  
 Die Reihenfolge der Auswertung des in der obigen Abbildung dargestellten Ausdrucks wird durch die Reihenfolge und die Assoziativität der Operatoren bestimmt:  
  
1.  Multiplikation \(\*\) weist die höchste Priorität in diesem Ausdruck auf. Daher wird der Teilausdruck `b * c` zuerst ausgewertet.  
  
2.  Addition \(\+\) besitzt die zweithöchste Priorität, sodass `a` dem Produkt von `b` und `c` hinzugefügt wird.  
  
3.  Nach links \(\<\<\) hat die niedrigste Priorität im Ausdruck, es gibt jedoch zwei Vorkommen.  Da der Left Shift\-Operator von links nach rechts gruppiert, wird zuerst der linke und dann der rechte Teilausdruck ausgewertet.  
  
 Wenn Teilausdrücke mit Klammern gruppiert werden, werden die Rangfolge sowie die Reihenfolge der Auswertung des Ausdrucks geändert, wie in der folgenden Abbildung gezeigt.  
  
 ![Auswertungsreihenfolge eines Ausdrucks mit Klammern](../cpp/media/vc38zv2.png "vc38ZV2")  
Reihenfolge der Auswertung von Ausdrücken mit Klammern  
  
 Ausdrücke, wie in der Abbildung oben, werden ausschließlich für ihre Nebeneffekte ausgewertet – in diesem Fall, um Informationen zum Standardausgabegerät zu übertragen.  
  
## Notation in Ausdrücken  
 Die Programmiersprache C\+\+ gibt beim Angeben von Operanden bestimmte Kompatibilitäten an.  In der folgenden Tabelle werden die Typen von Operanden gezeigt, die für Operatoren zulässig sind, die Operanden des Typs `type` benötigen.  
  
### Operandentypen, die für Operatoren zulässig sind  
  
|Typ erwartet|Typen zulässig|  
|------------------|--------------------|  
|`type`|**const** *type*<br /><br /> `volatile` *type*<br /><br /> `type`&<br /><br /> **const** `type`&<br /><br /> `volatile` `type`&<br /><br /> **volatile const** *type*<br /><br /> **volatile const** `type`&|  
|*type\**|`type`\* **const**`type`\* `volatile``type`\* **volatile const**|  
|**const** `type`|`type` **const** `type`**const** `type`&|  
|`volatile` `type`|`type` `volatile` `type``volatile` `type`&|  
  
 Da die vorangehenden Regeln immer in Kombination verwendet werden können, kann ein const\-Zeiger auf ein flüchtiges Objekt angegeben werden, wo ein Zeiger erwartet wird.  
  
## Mehrdeutige Ausdrücke  
 Bestimmte Ausdrücke sind mehrdeutig.  Diese Ausdrücke treten am häufigsten auf, wenn der Wert eines Objekts mehrfach im selben Ausdruck geändert wird.  Diese Ausdrücke basieren auf einer bestimmten Auswertungsreihenfolge, wenn sie von der Sprache nicht definiert wird.  Betrachten Sie das folgende Beispiel:  
  
```  
int i = 7;  
  
func( i, ++i );  
```  
  
 Die Programmiersprache C\+\+ gewährleistet nicht die Reihenfolge, in der Argumente zu einem Funktionsaufruf ausgewertet werden.  Daher könnte `func` im vorhergehenden Beispiel die Werte 7 und 8 oder 8 und 8 für die Parameter empfangen, je nachdem, ob die Parameter von links nach rechts oder von rechts nach links ausgewertet werden.  
  
## C\+\+\-Sequenzpunkte \(Microsoft\-spezifisch\)  
 Zwischen aufeinanderfolgenden "Sequenzpunkten" kann der Wert eines Objekts nur einmal durch einen Ausdruck geändert werden.  
  
 Die C\+\+\-Sprachendefinition gibt derzeit keine Sequenzpunkte an.  Microsoft C\+\+ verwendet dieselben Sequenzpunkte wie ANSI C für jeden beliebigen Ausdruck, der C\-Operatoren einbezieht und nicht überladene Operatoren beinhaltet.  Wenn Operatoren überladen werden, wird die Semantik von Operatorseqenzierung in Funktionsaufrufsequenzierung geändert.  Microsoft C\+\+ verwendet folgende Sequenzpunkte:  
  
-   Linker Operand des logischen AND\-Operators \(&&\).  Der linke Operand des logischen AND\-Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen.  Es gibt keine Garantie, dass der rechte Operand des logischen AND\-Operators ausgewertet wird.  
  
-   Linker Operand des logischen OR\-Operators \(&#124;&#124;\).  Der linke Operand des logischen OR\-Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen.  Es gibt keine Garantie, dass der rechte Operand des logischen OR\-Operators ausgewertet wird.  
  
-   Linker Operand des Komma\-Operators.  Der linke Operand des Komma\-Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen.  Beide Operanden des Komma\-Operators werden immer ausgewertet.  
  
-   Funktionsaufrufoperator.  Der Funktionsaufrufausdruck und alle Argumente für eine Funktion, einschließlich Standardargumente, werden ausgewertet und alle Nebeneffekte werden vor dem Eintritt in die Funktion abgeschlossen.  Es gibt keine festgelegte Reihenfolge der Auswertung unter den Argumenten bzw. beim Funktionsaufrufausdruck.  
  
-   Der erste Operand des bedingten Operators.  Der erste Operand des bedingten Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen.  
  
-   Das Ende eines vollständigen Initialisierungsausdrucks, wie das Ende einer Initialisierung in einer Deklarationsanweisung.  
  
-   Der Ausdruck in einer Ausdrucksanweisung.  Ausdrucksanweisungen bestehen aus einem optionalen Ausdruck, dem ein Semikolon \(;\) folgt.  Der Ausdruck wird vollständig für die Nebeneffekte ausgewertet.  
  
-   Der steuernde Ausdruck in einer Auswahlanweisung \("if" oder "switch"\).  Der Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden abgeschlossen, bevor der von der Auswahl abhängige Code ausgeführt wird.  
  
-   Der steuernde Ausdruck einer while\- oder do\-Anweisung.  Der Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden abgeschlossen, bevor eine beliebige Anweisung in der nächsten Iteration der while\- oder do\-Schleife ausgeführt wird.  
  
-   Jede der drei Ausdrücke einer for\-Anweisung.  Jeder Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden geschlossen, bevor zum nächsten Ausdruck gewechselt wird.  
  
-   Der Ausdruck in einer return\-Anweisung.  Der Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden abgeschlossen, bevor die Steuerung an die aufrufende Funktion zurückgegeben wird.  
  
## Siehe auch  
 [Ausdrücke](../cpp/expressions-cpp.md)