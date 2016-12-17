---
title: "&#220;berpr&#252;fte Iteratoren"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_SECURE_SCL"
  - "_SECURE_SCL_THROWS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "checked-Iteratoren"
  - "Iteratoren, checked"
  - "Sichere Bibliotheken"
  - "Sichere Bibliotheken, C++-Standardbibliothek"
  - "Sichere Standard-C++-Bibliothek"
ms.assetid: cfc87df8-e3d9-403b-ab78-e9483247d940
caps.latest.revision: 30
caps.handback.revision: "29"
ms.author: "corob"
manager: "ghogen"
---
# &#220;berpr&#252;fte Iteratoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Aktivierte Iteratoren stellen sicher, dass die Grenzen des Containers nicht überschrieben werden.  
  
 Aktivierte Iteratoren werden auf Releasebuilds und Debugbuilds angewendet.  Weitere Informationen zur Verwendung von Iteratoren beim Kompilieren im Debugmodus finden Sie unter [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md).  
  
## Hinweise  
 Informationen zur Deaktivierung von Warnungen, die durch aktivierte Iteratoren generiert werden, finden Sie unter [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
 Sie können folgendes Symbol mit der Funktion für aktivierte Iteratoren verwenden.  
  
 `_SECURE_SCL`  
 Wenn `_SECURE_SCL` als 1 definiert wird, verursacht die unsichere Verwendung von Iteratoren einen Laufzeitfehler und das Programm wird beendet.  Lautet die Definition 0, werden aktivierte Iteratoren deaktiviert.  Standardmäßig ist der Wert für `_SECURE_SCL` 0 für Releasebuilds und 1 für Debugbuilds.  
  
> [!IMPORTANT]
>  Verwenden Sie `_ITERATOR_DEBUG_LEVEL` zur Steuerung von [\_SECURE\_SCL](../standard-library/secure-scl.md).  Weitere Informationen finden Sie unter [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
 Wenn `_SECURE_SCL` als 1 definiert ist, werden folgende SCL\-Überprüfungen ausgeführt:  
  
-   Alle Standarditeratoren \(beispielsweise [vector::iterator](../Topic/vector::iterator.md)\) werden aktiviert.  
  
-   Wenn ein Ausgabeiterator ein aktivierter Iterator ist, erhalten Sie bei Aufrufen der Standardfunktion aktiviertes Verhalten \(beispielsweise [std::copy](../Topic/copy.md)\).  
  
-   Wenn der Ausgabeiterator ein nicht aktivierter Iterator ist, werden durch Aufrufe der Standardfunktion Compilerwarnungen verursacht.  
  
-   Die folgenden Funktionen generieren einen Laufzeitfehler, wenn ein Zugriff außerhalb der Grenzen des Containers erfolgt:  
  
|||||  
|-|-|-|-|  
|[basic\_string::operator](../Topic/basic_string::operator.md)|[bitset::operator](../Topic/bitset::operator.md)|[deque::back](../Topic/deque::back.md)|[deque::front](../Topic/deque::front.md)|  
|[deque::operator](../Topic/deque::operator.md)|[list::back](../Topic/list::back.md)|[list::front](../Topic/list::front.md)|[queue::back](../Topic/queue::back.md)|  
|[queue::front](../Topic/queue::front.md)|[vector::operator](../Topic/vector::operator.md)|[vector::back](../Topic/vector::back.md)|[vector::front](../Topic/vector::front.md)|  
  
 Wenn `_SECURE_SCL` als 0 definiert ist:  
  
-   Alle Standarditeratoren sind nicht aktiviert \(Iteratoren können über die Containergrenzen hinaus verschoben werden, was zu nicht definiertem Verhalten führt\).  
  
-   Wenn ein Ausgabeiterator ein aktivierter Iterator ist, erhalten Sie bei Aufrufen der Standardfunktion aktiviertes Verhalten \(beispielsweise `std::copy`\).  
  
-   Wenn ein Ausgabeiterator ein nicht aktivierter Iterator ist, erhalten Sie bei Aufrufen der Standardfunktion nicht aktiviertes Verhalten \(beispielsweise `std::copy`\).  
  
 Ein aktivierter Iterator bezieht sich auf einen Iterator, der `invalid_parameter_handler` aufruft, wenn Sie versuchen, über die Grenzen des Containers hinaus zu wechseln.  Weitere Informationen über `invalid_parameter_handler` finden Sie unter [Parametervalidierung](../c-runtime-library/parameter-validation.md).  
  
 [checked\_array\_iterator\-Klasse](../standard-library/checked-array-iterator-class.md) und [unchecked\_array\_iterator\-Klasse](../standard-library/unchecked-array-iterator-class.md) sind die Iteratoradapter, die aktivierte Iteratoren unterstützen.  
  
## Beispiel  
 Beim Kompilieren mit `_SECURE_SCL 1` tritt ein Laufzeitfehler auf, wenn Sie versuchen, mit dem Indizierungsoperator bestimmter Klassen auf ein Element zuzugreifen, das sich außerhalb der Grenzen des Containers befindet.  
  
```cpp  
// checked_iterators_1.cpp  
// cl.exe /Zi /MDd /EHsc /W4  
  
#define _ITERATOR_DEBUG_LEVEL 1  
// implies #define _SECURE_SCL 1  
  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main()   
{  
    vector<int> v;  
    v.push_back(67);  
  
    int i = v[0];  
    cout << i << endl;  
  
    i = v[1]; // triggers invalid parameter handler  
};  
  
```  
  
 Dieses Programm druckt "67" und zeigt ein Assertionsfehlerdialogfeld mit zusätzlichen Informationen über den Fehler an.  
  
## Beispiel  
 Wenn Sie mit `_SECURE_SCL 1` kompilieren, tritt entsprechend ein Laufzeitfehler auf, wenn Sie versuchen, mit dem Anfang oder dem Ende bestimmter Klassen auf ein Element zuzugreifen und der Container leer ist.  
  
```cpp  
// checked_iterators_2.cpp  
// cl.exe /Zi /MDd /EHsc /W4  
  
#define _ITERATOR_DEBUG_LEVEL 1  
// implies #define _SECURE_SCL 1  
  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main()   
{  
    vector<int> v;  
  
    int& i = v.front(); // triggers invalid parameter handler  
};  
  
```  
  
 Dieses Programm zeigt ein Assertionsfehlerdialogfeld mit zusätzlichen Informationen über den Fehler an.  
  
 Im folgenden Code werden verschiedene Anwendungsfälle für Iteratoren mit Kommentaren veranschaulicht.  
  
```cpp  
// cl.exe /MTd /EHsc /W4  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <iterator>  
#include <numeric>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v(16);  
    iota(v.begin(), v.end(), 0);  
    print("v: ", v);  
  
    // OK: vector::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to STL algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## Ausgabe  
 Das Kompilieren des im vorherigen Abschnitt gezeigten Codes mit `cl.exe /EHsc /W4 /MTd` führt zu folgender Compilerwarnung. Die Kompilierung in eine ausführbare Datei wird jedoch ohne Fehler ausgeführt:  
  
```  
algorithm(1026) : warning C4996: 'std::_Transform1': Function call with parameters that may be unsafe - this call rel  
ies on the caller to check that the passed values are correct. To disable this warning, use -D_SCL_SECURE_NO_WARNINGS. See documentation on how to use Visual C++ 'Checked Iterators'  
```  
  
 Das Ausführen der ausführbaren Konsolen\-App\-Datei ergibt folgende Ausgabe:  
  
```  
v: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15  
v2: 0 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30  
v3: 0 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45  
a4: 0 4 8 12 16 20 24 28 32 36 40 44 48 52 56 60  
a5: 0 5 10 15 20 25 30 35 40 45 50 55 60 65 70 75  
a6: 0 6 12 18 24 30 36 42 48 54 60 66 72 78 84 90  
a7: 0 7 14 21 28 35 42 49 56 63 70 77 84 91 98 105  
a8: 0 8 16 24 32 40 48 56 64 72 80 88 96 104 112 120  
```  
  
## Siehe auch  
 [STL\-Übersicht](../standard-library/cpp-standard-library-overview.md)   
 [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)