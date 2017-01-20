---
title: "for-Anweisung (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for-Schlüsselwort [C++]"
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# for-Anweisung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Führt eine Anweisung wiederholt aus, bis die Bedingung false ergibt.  Informationen zur bereichsbasierten for\-Anweisung finden Sie unter [Bereichsbasiert für Anweisung \(C\+\+\)](../cpp/range-based-for-statement-cpp.md).  
  
## Syntax  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## Hinweise  
 Verwenden Sie die `for`\-Anweisung, zum Erstellen von Schleifen, die eine angegebene Anzahl von Wiederholungen ausführen müssen.  
  
 Die `for`\-Anweisung besteht aus drei optionalen, in der folgenden Tabelle dargestellten, Teilen.  
  
### for\-Schleifenelemente  
  
|Syntaxname|Ausführung bei|Beschreibung|  
|----------------|--------------------|------------------|  
|`init-expression`|Vor jedem anderen Element der **for**\-Anweisung wird `init-expression` nur einmal ausgeführt.  Das Steuerelement wird dann an `cond-expression` übergeben.|Wird häufig zum Initialisieren von Schleifenindizes verwendet.  Es können Ausdrücke oder Deklarationen enthalten sein.|  
|`cond-expression`|Vor der Ausführung jeder Iteration von `statement`, einschließlich der ersten Iteration.  `statement` wird nur ausgeführt, wenn `cond-expression` den Wert „True“ \(ungleich 0 \(null\)\) annimmt.|Ein Ausdruck, der einen Ganzzahltyp oder einen Klassentyp ergibt, der über eine eindeutige Konvertierung in einen Ganzzahltyp verfügt.  Wird normalerweise zum Testen von Beendigungskriterien für Schleifen verwendet.|  
|`loop-expression`|Am Ende jeder Iteration von `statement`.  Nachdem `loop-expression` ausgeführt wird, wird `cond-expression` ausgewertet.|Wird normalerweise zum Erhöhen von Schleifenindizes verwendet.|  
  
 Die folgenden Beispiele zeigen verschiedene Verwendungsmöglichkeiten der `for`\-Anweisung.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    // The counter variable can be declared in the init-expression.  
    for (int i = 0; i < 2; i++ ){   
       cout << i;  
    }  
    // Output: 01  
    // The counter variable can be declared outside the for loop.  
    int i;  
    for (i = 0; i < 2; i++){  
        cout << i;  
    }  
    // Output: 01  
    // These for loops are the equivalent of a while loop.  
    i = 0;  
    while (i < 2){  
        cout << i++;  
    }  
}  
    // Output: 012  
```  
  
 `init-expression` und `loop-expression` können mehrere durch Kommas getrennte Anweisungen enthalten.  Beispiel:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
    int i, j;  
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {  
        cout << "i + j = " << (i + j) << '\n';  
    }  
}  
    // Output:  
    i + j = 15  
    i + j = 17  
    i + j = 19  
```  
  
 Der `loop-expression` kann erweitert oder verringert werden oder in anderer Weise geändert werden.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
for (int i = 10; i > 0; i--) {  
        cout << i << ' ';  
    }  
    // Output: 10 9 8 7 6 5 4 3 2 1  
    for (int i = 10; i < 20; i = i+2) {  
        cout << i << ' ';  
    }  
    // Output: 10 12 14 16 18  
```  
  
 Eine `for`\-Schleife wird beendet, wenn [break](../cpp/break-statement-cpp.md), [return](../cpp/return-statement-cpp.md) oder [goto](../cpp/goto-statement-cpp.md) \(an eine Anweisung mit Bezeichnung außerhalb der **for**\-Schleife\) innerhalb von `statement` ausgeführt wird.  Mit einer [continue](../cpp/continue-statement-cpp.md)\-Anweisung in einer `for`\-Schleife wird nur die aktuelle Iteration beendet.  
  
 Wenn `cond-expression` ausgelassen wird, gilt sie als "true", und die **for**\-Schleife wird nicht ohne ein `break`, `return` oder `goto` innerhalb der `statement` beendet.  
  
 Obwohl die drei Felder der `for`\-Anweisung normalerweise zum Initialisieren, Testen auf Beendigung und Inkrementieren verwendet werden, sind sie nicht auf dieser Verwendungsmöglichkeiten begrenzt.  Beispielsweise gibt der folgende Code die Zahlen 0 bis 4 aus.  In diesem Fall handelt es sich bei `statement` um die null\-Anweisung:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    int i;  
    for( i = 0; i < 5; cout << i << '\n', i++){  
        ;  
    }  
}  
```  
  
## for\-Schleifen und der C\+\+\-Standard  
 Der C\+\+\-Standard besagt, dass eine in einer `for` \- Schleife deklarierte Variable den Gültigkeitsbereich nach Beenden der `for` \- Schleife verlassen soll.  Beispiel:  
  
```cpp  
for (int i = 0 ; i < 5 ; i++) {  
   // do something  
}  
// i is now out of scope under /Za or /Zc:forScope  
```  
  
 Standardmäßig bleibt unter [\/Ze](../build/reference/za-ze-disable-language-extensions.md) eine in einer `for` \- Schleife deklarierte Variable bis zum Beenden der `for` \- Schleife des einschließenden Bereichs im Bereich.  
  
 [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) ermöglicht Standardverhalten der in for\-Schleifen deklarierten Variablen, ohne dass \/Za angegeben werden muss.  
  
 Es ist auch möglich, die Bereichsunterschiede der `for`\-Schleife wie folgt zum erneuten Deklarieren der Variablen unter \/Ze verwenden:  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 Dies imitiert das Standardverhalten einer Variablen genauer, die in einer `for`\-Schleife deklariert wurde, für die zum Verlassen des Bereichs nach dem Ausführen der Schleife Variablen erforderlich sind, die in einer `for`\-Schleife deklariert werden.  Beim Deklarieren einer Variablen in einer `for`\-Schleife, stuft der Compiler sie intern zu einer lokalen Variablen im einschließenden Bereich der `for`\-Schleife auf. Dies geschieht auf dann, wenn bereits eine lokale Variable mit dem gleichen Namen vorhanden ist.  
  
## Siehe auch  
 [Iterationsanweisungen](../cpp/iteration-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [while\-Anweisung \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [do\-while\-Anweisung \(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [Bereichsbasiert für Anweisung \(C\+\+\)](../cpp/range-based-for-statement-cpp.md)