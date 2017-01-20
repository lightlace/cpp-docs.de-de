---
title: "Logischer AND-Operator: &amp;&amp;"
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
  - "&&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "&&-Operator"
  - "AND-Operator"
  - "Logischer AND-Operator"
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Logischer AND-Operator: &amp;&amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
expression   
&&  
 expression  
  
```  
  
## Hinweise  
 Der logische AND\-Operator \(**&&**\) gibt den Booleschen Wert mit **True** an, wenn beide Operanden **True** sind. Ansonsten ist der Wert **False**.  Die Operanden werden vor der Auswertung implizit in den Typ `bool` konvertiert. Das Ergebnis ist ein `bool`\-Typ.  Das logische AND weist eine Assoziativität von links nach rechts auf.  
  
 Die Operanden für den logischen AND\-Operator müssen nicht vom gleichen Typ sein, aber sie müssen Ganzzahltypen oder Zeigertypen sein.  Die Operanden sind im Allgemeinen relationale oder Gleichheitsausdrücke.  
  
 Der erste Operand wird vollständig ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor die Auswertung des logischen AND\-Ausdrucks fortgesetzt wird.  
  
 Der zweite Operand wird nur dann ausgewertet, wenn der erste Operand als true \(ungleich Null\) ausgewertet wird.  Diese Auswertung eliminiert die unnötige Auswertung des zweiten Operanden, wenn der Ausdruck der logischen AND\-Operation gleich false ist.  Mithilfe dieser Kurzschlussauswertung können Sie Dereferenzierungen durch NULL\-Zeiger verhindern, wie im folgenden Beispiel gezeigt:  
  
```  
char *pch = 0;  
...  
(pch) && (*pch = 'a');  
```  
  
 Wenn `pch` null \(0\) ist, wird die rechte Seite des Ausdrucks niemals ausgewertet.  Daher ist die Zuweisung durch einen NULL\-Zeiger unmöglich.  
  
## Operator\-Schlüsselwort für &&  
 Der **and**\-Operator ist die ausgeschriebene Variante von **&&**.  Es gibt zwei Möglichkeiten, wie Sie in Programmen auf den Operator **and** zugreifen können: Fügen Sie die Headerdatei `iso646.h` ein, oder kompilieren Sie mit der Compileroption [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Spracherweiterungen deaktivieren\).  
  
## Beispiel  
  
```  
// expre_Logical_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical AND  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b && b < c yields "  
         << (a < b && b < c) << endl  
         << "The false expression "  
         << "a > b && b < c yields "  
         << (a > b && b < c) << endl;  
}  
```  
  
## Siehe auch  
 [Logische Operatoren](../misc/logical-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C\-Operatoren \(logisch\)](../c-language/c-logical-operators.md)