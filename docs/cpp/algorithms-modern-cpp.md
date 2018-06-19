---
title: Algorithmen (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fdd5742bb86992ce20f5a52f587c8557d46a97eb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412295"
---
# <a name="algorithms-modern-c"></a>Algorithmen (Modern C++)
Für moderne C++-Programmierung empfehlen wir die Verwendung von der Algorithmen in der [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md). Im Folgenden sind einige wichtige Beispiele aufgeführt:  
  
-   `for_each`. Dies ist der Standarddurchlaufalgorithmus. (Auch `transform` für Not-in-Place-Semantik.)  
  
-   `find_if`. Dies ist der Standardsuchalgorithmus.  
  
-   `sort`, `lower_bound` und weitere Standardsortier- und -suchalgorithmen.  
  
 Verwenden Sie zum Schreiben eines Vergleichsoperators strict `<` und *benannte Lambdas* falls möglich.  
  
```cpp  
auto comp = [](const widget& w1, const widget& w2)  
      { return w1.weight() < w2.weight(); }  
  
sort( v.begin(), v.end(), comp );  
  
auto i = lower_bound( v.begin(), v.end(), comp );  
```  
  
## <a name="loops"></a>Schleifen  
 Verwenden Sie nach Möglichkeit bereichsbasierte `for` -Schleifen oder algorithmusaufrufe oder beides statt von Hand geschriebene Schleifen.`copy`, `transform`, `count_if`, `remove_if`, usw. eignen sich wesentlich besser als von Hand geschriebene Schleifen, und da ihre Absicht offensichtlich ist und sie es einfacher machen, fehlerfreien Code zu schreiben. Viele C++-Standardbibliothek Algorithmen haben außerdem implementierungsoptimierungen, die effizienter zu gestalten.  
  
 Anstelle des alten C++ wie:  
  
```cpp  
for ( auto i = strings.begin(); i != strings.end(); ++i ) {  
   /* ... */  
}  
  
auto i = v.begin();  
  
for ( ; i != v.end(); ++i ) {  
  if (*i > x && *i < y) break;  
}  
```  
  
 Verwenden Sie modernes C++ wie:  
  
```cpp  
for_each( begin(strings), end(strings), [](string& s) {  
   // ...  
} );  
  
auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; } );  
```  
  
### <a name="range-based-for-loops"></a>Bereichsbasierte For-Schleifen  
 Die bereichsbasierte `for` Schleife ist eine C ++ 11-Sprachfunktion, keine C++-Standardbibliothek-Algorithmus. Sie verdient jedoch im Rahmen dieser Diskussion über Schleifen Erwähnung. Bereichsbasierte `for`-Schleifen sind eine Erweiterung des `for`-Schlüsselworts und bieten eine komfortable und effiziente Möglichkeit, Schleifen zu schreiben, die einen Wertebereich durchlaufen. C++-Standardbibliothek Container, Zeichenfolgen und Arrays sind vordefinierte für bereichsbasierte `for` Schleifen. Um diese neue Iterationssyntax für den benutzerdefinierten Typ zu aktivieren, fügen Sie die folgende Unterstützung hinzu:  
  
-   Eine `begin`-Methode, die einen Iterator zum Anfang der Struktur zurückgibt und eine `end`-Methode, die einen Iterator an das Ende der Struktur zurückgibt.  
  
-   Unterstützung im Iterator für diese Methoden: `operator*`, `operator!=` und `operator++` (Präfixversion).  
  
 Diese Methoden können entweder Member oder eigenständige Funktionen sein.  
  
## <a name="random-numbers"></a>Zufallszahlen  
 Es ist bekannt, dass die alte Funktion CRT `rand()`-Funktion viele Fehler enthält, die ausführlich in der C++-Community erläutert wurden. In modernem C++, haben Sie keinen für den Umgang mit diesen Mängel – ebenso wenig müssen Sie eigene gleichmäßig verteilten Zufallszahlen-Generator auswählen – da die Tools zum schnell und einfach erstellen sie in der C++-Standardbibliothek verfügbar sind, entsprechend [ \<random >](../standard-library/random.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)