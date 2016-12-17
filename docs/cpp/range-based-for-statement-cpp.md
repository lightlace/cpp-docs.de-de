---
title: "Bereichsbasiert f&#252;r Anweisung (C++)"
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
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Bereichsbasiert f&#252;r Anweisung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Führt `statement` für jedes Element in `expression` wiederholt und nacheinander aus.  
  
## Syntax  
  
```  
  
      for ( for-range-declaration : expression )  
   statement   
```  
  
## Hinweise  
 Verwenden Sie die bereichsbasierte `for`\-Anweisung zum Erstellen von Schleifen, die einem "Bereich" ausführen müssen, der definiert ist als alles, was durchlaufen werden kann, zum Beispiel, `std::vector`, oder eine andere STL\-Sequenz, deren Gültigkeitsbereich von `begin()` und `end()` definiert wird.  Der im `for-range-declaration`\-Teil deklarierte Name ist zur `for`\-Anweisung lokal und kann in `expression` oder `statement` nicht neu deklariert werden.  Beachten Sie, dass das [auto](../cpp/auto-cpp.md)\-Schlüsselwort im `for-range-declaration`\-Teil der Anweisung bevorzugt wird.  
  
 In diesem Code wird die Verwendung von `for`\-Schleifen mit Bereichen zum Durchlaufen eines Arrays und eines Vektors veranschaulicht:  
  
```cpp  
  
// range-based-for.cpp  
// compile by using: cl /EHsc /nologo /W4  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
    // Basic 10-element integer array.  
    int x[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };  
  
    // Range-based for loop to iterate through the array.  
    for( int y : x ) { // Access by value using a copy declared as a specific type.   
                       // Not preferred.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    // The auto keyword causes type inference to be used. Preferred.  
  
    for( auto y : x ) { // Copy of 'x', almost always undesirable  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( auto &y : x ) { // Type inference by reference.  
        // Observes and/or modifies in-place. Preferred when modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( const auto &y : x ) { // Type inference by reference.  
        // Observes in-place. Preferred when no modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
    cout << "end of integer array test" << endl;  
    cout << endl;  
  
    // Create a vector object that contains 10 elements.  
    vector<double> v;  
    for (int i = 0; i < 10; ++i) {  
        v.push_back(i + 0.14159);  
    }  
  
    // Range-based for loop to iterate through the vector, observing in-place.  
    for( const auto &j : v ) {  
        cout << j << " ";  
    }  
    cout << endl;  
    cout << "end of vector test" << endl;  
}  
  
```  
  
 Es folgt die Ausgabe:  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `end of integer array test`  
  
 `0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159`  
  
 `end of vector test`  
  
 Eine bereichsbasierte `for`\-Schleife wird beendet, wenn in `statement` einer der folgenden Befehle: [break](../cpp/break-statement-cpp.md), [return](../cpp/return-statement-cpp.md) oder [goto](../cpp/goto-statement-cpp.md), für einer Anweisung mit Bezeichnung außerhalb der bereichsbasierten **for**\-Schleife ausgeführt wird.  Mit einer [continue](../cpp/continue-statement-cpp.md)\-Anweisung in einer bereichsbasierten `for`\-Schleife wird nur die aktuelle Iteration beendet.  
  
 Beachten Sie diese Punkte zu bereichsbasierten `for`\-Schleifen:  
  
-   Erkennt Arrays automatisch.  
  
-   Erkennt Container, die über `.begin()` und `.end()` verfügen.  
  
-   Verwendet die argumentabhängigen Suche `begin()` und `end()` für alles andere.  
  
## Siehe auch  
 [auto](../cpp/auto-cpp.md)   
 [Iterationsanweisungen](../cpp/iteration-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [while\-Anweisung \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [do\-while\-Anweisung \(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [for\-Anweisung \(C\+\+\)](../cpp/for-statement-cpp.md)