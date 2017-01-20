---
title: "Inkrementierungs- und Dekrementierungsoperatoren in Pr&#228;fixnotation: ++ und --"
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
  - "--"
  - "++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-- (Operator), Präfixdekrementoperatoren"
  - "++-Operator, Präfixinkrementoperatoren"
  - "Dekrementoperatoren"
  - "Dekrementoperatoren, Syntax"
  - "Inkrementoperatoren, Syntax"
  - "Operatoren [C++], Dekrement"
  - "Operatoren [C++], Inkrement"
ms.assetid: 45ea7fc7-f279-4be9-a216-1d9a0ef9eb7b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Inkrementierungs- und Dekrementierungsoperatoren in Pr&#228;fixnotation: ++ und --
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
++ unary-expression –– unary-expression  
```  
  
## Hinweise  
 Der Präfixdekrementoperator \(`++`\) fügt einen Wert zu seinem Operanden hinzu. Das Ergebnis des Ausdrucks ist dieser inkrementierte Wert.  Der Operand muss ein l\-Wert sein, der kein **Const**\-Typ ist.  Das Ergebnis ist ein l\-Wert des gleichen Typs wie der Operand.  
  
 Der Präfixdekrementoperator \(**––**\) entspricht dem Präfixinkrementoperator. Der einzige Unterschied besteht darin, dass der Operand um einen Wert verringert wird. Das Ergebnis ist dieser dekrementierte Wert.  
  
 Sowohl Präfix\- als auch Postfixinkrement und Dekrementoperatoren beeinflussen ihre Operanden.  Der wesentliche Unterschied zwischen ihnen besteht in der Reihenfolge von Inkrement und Dekrement bei der Auswertung eines Ausdrucks.  \(Weitere Informationen finden Sie unter [Postfix\-Inkrementoperatoren und Postfix\-Dekrementoperatoren](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)\). In der Präfix\-Form findet das Inkrement oder Dekrement statt, bevor der Wert in der Ausdrucksauswertung verwendet wird, daher ist der Wert des Ausdrucks ungleich dem Wert des Operanden.  In der Postfix\-Form findet das Inkrement oder Dekrement statt, nachdem der Wert in der Ausdrucksauswertung verwendet wird, daher ist der Wert des Ausdrucks der gleiche wie der Wert des Operanden.  Zum Beispiel gibt das folgende Programm "`++i = 6`" aus:  
  
```  
// expre_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int i = 5;  
   cout << "++i = " << ++i << endl;  
}  
```  
  
 Ein Operand vom Typ "Ganzzahl" oder "Gleitkomma" wird durch den ganzzahligen Wert 1 inkrementiert oder dekrementiert.  Der Ergebnistyp entspricht dem Operandentyp.  Ein Operand vom Zeigertyp wird um die Größe des von ihm adressierten Objekts inkrementiert oder dekrementiert.  Ein inkrementierter Zeiger verweist auf das nächste Objekt. Ein dekrementierter Zeiger verweist auf das vorherige Objekt.  
  
 Da Inkrement\- und Dekrementoperatoren Nebeneffekte haben, kann die Verwendung von Ausdrücken mit Inkrement\- oder Dekrementoperatoren unerwünschte Ergebnisse in einem [\-Präprozessormakro](../preprocessor/macros-c-cpp.md) haben.  Betrachten Sie das folgende Beispiel:  
  
```  
// expre_Increment_and_Decrement_Operators2.cpp  
#define max(a,b) ((a)<(b))?(b):(a)  
  
int main()  
{  
   int i = 0, j = 0, k;  
   k = max( ++i, j );  
}  
```  
  
 Das Makro wird wie folgt erweitert:  
  
```  
k = ((++i)<(j))?(j):(++i);  
```  
  
 Wenn `i` größer oder gleich `j` oder um 1 kleiner als `j` ist, wird es zweimal inkrementiert.  
  
> [!NOTE]
>  C\+\+\-Inlinefunktionen sind in vielen Fällen Makros vorzuziehen, da diese Nebeneffekte, wie die hier beschriebenen, ausschließen und der Programmiersprache die weitere Ausführung vollständigerer Typüberprüfung ermöglichen.  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Inkrementierungs\- und Dekrementierungsoperatoren in Präfixnotation](../c-language/prefix-increment-and-decrement-operators.md)