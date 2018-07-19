---
title: Bereichsbasiert für Anweisung (C++) | Microsoft-Dokumentation
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
ms.openlocfilehash: 1284e4f6e096ab8021c597b841a8e983673561bd
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943592"
---
# <a name="range-based-for-statement-c"></a>Bereichsbasiert für Anweisung (C++)
Führt `statement` für jedes Element in `expression` wiederholt und nacheinander aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
for ( for-range-declaration : expression )  
   statement   
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die bereichsbasierte **für** Anweisung zum Erstellen von Schleifen, die einem "Bereich", die als nichts definiert ist, die Sie durchlaufen können ausführen müssen, z. B. `std::vector`, oder eine beliebige andere C++-Standard-Bibliothek Sequenz, deren Bereich wird definiert, indem eine `begin()` und `end()`. Der Name, der in deklariert wird die `for-range-declaration` Teil ist bezogen auf die **für** Anweisung und kann nicht neu deklariert in `expression` oder `statement`. Beachten Sie, dass die [automatisch](../cpp/auto-cpp.md) Schlüsselwort wird bevorzugt, der `for-range-declaration` Teil der Anweisung. 

 **Neues in Visual Studio 2017:** bereichsbasierte for-Schleifen erfordern nicht mehr, dass begin() und end() Objekte des gleichen Typs zurückgeben. Dadurch kann end() ein Sentinelobjekt zurückgeben, das von Bereichen verwendet wird, die im Ranges-V3-Vorschlag definiert sind. Weitere Informationen finden Sie unter [Generalizing the Range-Based For Loop (Bereichsbasierte for-Schleife generalisieren)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html) und [range-v3 library on GitHub (Range-v3-Bibliothek auf GitHub)](https://github.com/ericniebler/range-v3).
  
 Dieser Code zeigt, wie Sie mit bereichsbasierten **für** Schleifen auf, um ein Array und einen Vektor durchlaufen:  
  
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

```Output
 1 2 3 4 5 6 7 8 9 10  
  
 1 2 3 4 5 6 7 8 9 10  
  
 1 2 3 4 5 6 7 8 9 10  
  
 1 2 3 4 5 6 7 8 9 10  
  
 `end of integer array test`  
  
 `0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159`  
  
 `end of vector test`  
```

 Eine bereichsbasierte **für** Schleife wird beendet, wenn eines der folgenden in `statement` ausgeführt wird: ein [Break](../cpp/break-statement-cpp.md), [zurückgeben](../cpp/return-statement-cpp.md), oder [Goto](../cpp/goto-statement-cpp.md) auf eine bezeichnete Anweisung außerhalb der bereichsbasierten **für** Schleife. Ein [weiterhin](../cpp/continue-statement-cpp.md) -Anweisung in einer bereichsbasierten **für** -Schleife wird nur die aktuelle Iteration beendet.  
  
 Bedenken Sie diese Fakten zu bereichsbasierten **für**:  
  
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