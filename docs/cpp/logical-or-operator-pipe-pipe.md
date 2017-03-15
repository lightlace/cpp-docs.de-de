---
title: "Logischer OR-Operator: ||"
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
  - "||"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "||-Operator"
  - "Logischer OR-Operator"
  - "OR-Operator"
  - "OR-Operator, Logisch"
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Logischer OR-Operator: ||
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
logical-or-expression   
||  
 logical-and-expression  
  
```  
  
## Hinweise  
 Der logische OR\-Operator \(`||`\) gibt den booleschen Wert **true** zurück, wenn einer oder beide Operanden **true** ist. Ansonsten ist der Wert **false**.  Die Operanden werden vor der Auswertung implizit in den Typ `bool` konvertiert. Das Ergebnis ist ein `bool`\-Typ.  Das logische OR weist eine Assoziativität von links nach rechts auf.  
  
 Die Operanden für den logischen OR\-Operator müssen nicht vom gleichen Typ sein, aber sie müssen Ganzzahltypen oder Zeigertypen sein.  Die Operanden sind im Allgemeinen relationale oder Gleichheitsausdrücke.  
  
 Der erste Operand wird vollständig ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor die Auswertung des logischen OR\-Ausdrucks fortgesetzt wird.  
  
 Der zweite Operand wird nur ausgewertet, wenn der erste Operand als false \(0\) ausgewertet wird.  Diese Auswertung eliminiert die unnötige Auswertung des zweiten Operanden, wenn der logische OR\-Ausdruck "true" ist.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 Im Beispiel oben, wenn `x` entweder gleich `w`, `y` oder `z` ist, wird das zweite Argument für die `printf`\-Funktion mit "true" ausgewertet, und der Wert 1 wird ausgegeben.  Andernfalls wird dies mit "false" ausgewertet, und der Wert 0 \(null\) wird ausgegeben.  Sobald eine der Bedingungen mit dem Ergebnis "true" ausgewertet wird, wird die Auswertung beendet.  
  
## Operator\-Schlüsselwort für "&#124;&#124;"  
 Der **or**\-Operator ist die Textentsprechung von `||`.  Es gibt zwei Möglichkeiten, wie Sie in Programmen auf den Operator **or** zugreifen können: Fügen Sie die Headerdatei `iso646.h` ein, oder kompilieren Sie mit der Option [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Spracherweiterungen deaktivieren\).  
  
## Beispiel  
  
```  
// expre_Logical_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical OR  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b || b > c yields "  
         << (a < b || b > c) << endl  
         << "The false expression "  
         << "a > b || b > c yields "  
         << (a > b || b > c) << endl;  
}  
```  
  
## Siehe auch  
 [Logische Operatoren](../misc/logical-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C\-Operatoren \(logisch\)](../c-language/c-logical-operators.md)