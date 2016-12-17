---
title: "Algorithmen (Modern C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Algorithmen (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für moderne C\+\+\-Programmierung wird empfohlen, die Algorithmen in der [Standardvorlagenbibliothek](../standard-library/cpp-standard-library-reference.md) \(STL\) zu verwenden.  Im Folgenden sind einige wichtige Beispiele aufgeführt:  
  
-   `for_each`. Dies ist der Standarddurchlaufalgorithmus. \(Auch `transform` für Not\-in\-Place\-Semantik.\)  
  
-   `find_if`. Dies ist der Standardsuchalgorithmus.  
  
-   `sort`, `lower_bound` und weitere Standardsortier\- und \-suchalgorithmen.  
  
 Verwenden Sie zum Schreiben eines Vergleichsoperators strict `<` und *benannte Lambdas*, falls möglich.  
  
```cpp  
  
auto comp = [](const widget& w1, const widget& w2)  
      { return w1.weight() < w2.weight(); }  
  
sort( v.begin(), v.end(), comp );  
  
auto i = lower_bound( v.begin(), v.end(), comp );  
  
```  
  
## Schleifen  
 Verwenden Sie nach Möglichkeit bereichsbasierte `for`\-Schleifen oder Algorithmusaufrufe oder beides statt von Hand geschriebener Schleifen.  `copy`, `transform`, `count_if`, `remove_if` usw. eignen sich wesentlich besser als von Hand geschriebene Schleifen, da ihre Absicht offensichtlich ist und sie es einfacher machen, fehlerfreien Code zu schreiben.  Viele STL\-Algorithmen haben außerdem Implementierungsoptimierungen, die sie effizienter machen.  
  
 Anstelle des alten C\+\+ wie:  
  
```cpp  
  
for( auto i = strings.begin(); i != strings.end(); ++i ) {  
  :::  
  :::  
}  
  
auto i = v.begin();  
  
for( ; i != v.end(); ++i ) {  
  if (*i > x && *i < y) break;  
}  
  
```  
  
 Verwenden Sie modernes C\+\+ wie:  
  
```cpp  
  
for_each( begin(strings), end(strings), [](string& s) {  
  :::  
  :::  
} );  
auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; }  );  
  
```  
  
### Bereichsbasierte For\-Schleifen  
 Die bereichsbasierte `for`\-Schleife ist eine C\+\+11\-Sprachfunktion, kein STL\-Algorithmus.  Sie verdient jedoch im Rahmen dieser Diskussion über Schleifen Erwähnung.  Bereichsbasierte `for`\-Schleifen sind eine Erweiterung des `for`\-Schlüsselworts und bieten eine komfortable und effiziente Möglichkeit, Schleifen zu schreiben, die einen Wertebereich durchlaufen.  STL\-Container, Zeichenfolgen und Arrays sind für bereichsbasierte `for`\-Schleifen einsatzbereit.  Um diese neue Iterationssyntax für den benutzerdefinierten Typ zu aktivieren, fügen Sie die folgende Unterstützung hinzu:  
  
-   Eine `begin`\-Methode, die einen Iterator zum Anfang der Struktur zurückgibt und eine `end`\-Methode, die einen Iterator an das Ende der Struktur zurückgibt.  
  
-   Unterstützung im Iterator für diese Methoden: `operator*`, `operator!=` und `operator++` \(Präfixversion\).  
  
 Diese Methoden können entweder Member oder eigenständige Funktionen sein.  
  
## Zufallszahlen  
 Es ist bekannt, dass die alte Funktion CRT `rand()`\-Funktion viele Fehler enthält, die ausführlich in der C\+\+\-Community erläutert wurden.  In modernem C\+\+ brauchen Sie sich um diese Schwachpunkt nicht zu kümmern. Sie brauchen auch keinen eigenen Generator für gleichmäßig verteilte Zufallszahlen erfinden, da die Tools zum schnellen und einfachen Erstellen solcher Zahlen in STL verfügbar sind, wie in [\<random\>](../standard-library/random.md) dargestellt.  
  
## Siehe auch  
 [Willkommen zurück bei C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)