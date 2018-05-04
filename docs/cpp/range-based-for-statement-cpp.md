---
title: Range-based for-Anweisung (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc60c1efc307f30c06accdd7404cb35c135dae5b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="range-based-for-statement-c"></a>Bereichsbasiert für Anweisung (C++)
Führt `statement` für jedes Element in `expression` wiederholt und nacheinander aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      for ( for-range-declaration : expression )  
   statement   
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die bereichsbasierte `for` Anweisung zum Erstellen von Schleifen, die ausführen müssen, einem "Bereich", der als nichts definiert ist, die durchlaufen werden kann – z. B. `std::vector`, oder eine andere C++-Standardbibliothek Sequenz, deren Gültigkeitsbereich durch eine definiertist,`begin()` und `end()`. Der im `for-range-declaration`-Teil deklarierte Name ist zur `for`-Anweisung lokal und kann in `expression` oder `statement` nicht neu deklariert werden. Beachten Sie, dass die [Auto](../cpp/auto-cpp.md) Schlüsselwort wird bevorzugt, der `for-range-declaration` Teil der Anweisung. 

 **Neues in Visual Studio 2017:** bereichsbasierte für Schleifen nicht mehr benötigt wird, dass begin() und end() Objekte vom gleichen Typ zurückgeben. Dadurch kann end() ein Sentinelobjekt zurückgeben, das von Bereichen verwendet wird, die im Ranges-V3-Vorschlag definiert sind. Weitere Informationen finden Sie unter [Generalizing the Range-Based For Loop (Bereichsbasierte for-Schleife generalisieren)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html) und [range-v3 library on GitHub (Range-v3-Bibliothek auf GitHub)](https://github.com/ericniebler/range-v3).
  
 Dieser Code zeigt, wie bereichsbasierte `for` Schleifen ein Array und einen Vektor durchlaufen:  
  
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
  
    for( const auto &y : x ) { // Type inference by const reference.  
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
  
 Eine bereichsbasierte `for` Schleife beendet, wenn eines der folgenden in `statement` ausgeführt wird: ein [Break](../cpp/break-statement-cpp.md), [zurückgeben](../cpp/return-statement-cpp.md), oder [Goto](../cpp/goto-statement-cpp.md) eine Anweisung mit Bezeichnung außerhalb der bereichsbasierte **für** Schleife. Ein [weiterhin](../cpp/continue-statement-cpp.md) -Anweisung in einer bereichsbasierten `for` -Schleife wird nur die aktuelle Iteration beendet.  
  
 Beachten Sie diese Punkte zu bereichsbasierten `for`-Schleifen:  
  
-   Erkennt Arrays automatisch.  
  
-   Erkennt Container, die über `.begin()` und `.end()` verfügen.  
  
-   Verwendet die argumentabhängigen Suche `begin()` und `end()` für alles andere.  
  
## <a name="see-also"></a>Siehe auch  
 [Auto](../cpp/auto-cpp.md)   
 [Iterationsanweisungen](../cpp/iteration-statements-cpp.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [while-Anweisung (C++)](../cpp/while-statement-cpp.md)   
 [do-while-Anweisung (C++)](../cpp/do-while-statement-cpp.md)   
 [for-Anweisung (C++)](../cpp/for-statement-cpp.md)