---
title: Algorithmen (Modern C++) | Microsoft-Dokumentation
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
ms.openlocfilehash: 604b58f7f8f6074c16effa3220d17bc00c44f5b8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214313"
---
# <a name="algorithms-modern-c"></a>Algorithmen (Modern C++)

Für moderne C++-Programmierung empfehlen wir die Verwendung von der Algorithmen in der [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md). Im Folgenden sind einige wichtige Beispiele aufgeführt:

- **For_each**, dies ist der standarddurchlaufalgorithmus. (Auch **transformieren** für nicht-in-Place-Semantik.)

- **Find_if**, dies ist der standardsuchalgorithmus.

- **Sortierung**, **Lower_bound**, und weitere sortieren und Durchsuchen von Algorithmen.

Verwenden Sie zum Schreiben eines Vergleichsoperators strict **<** und *benannte Lambdas* nach Möglichkeit.

```cpp  
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );  
```

## <a name="loops"></a>Schleifen

Verwenden Sie nach Möglichkeit bereichsbasierte **für** -Schleifen oder algorithmusaufrufe oder beides statt von Hand geschriebener Schleifen. **Kopie**, **transformieren**, **Count_if**, **Remove_if**, und usw. sind wesentlich besser als Hand geschriebene Schleifen, da ihre Absicht offensichtlich ist und sie erleichtern Sie, fehlerfreien Code zu schreiben. Relativ viele Algorithmen für C++-Standardbibliothek haben außerdem implementierungsoptimierungen, die sie effizienter machen.

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

Die bereichsbasierte **für** Schleife ist eine C ++ 11-Sprachfunktion, nicht auf ein C++-Standardbibliothek-Algorithmus. Sie verdient jedoch im Rahmen dieser Diskussion über Schleifen Erwähnung. Bereichsbasierte **für** -Schleifen sind eine Erweiterung von der **für** Schlüsselwort und bieten eine komfortable und effiziente Möglichkeit, Schleifen schreiben, die einen Wertebereich durchlaufen. C++-Standardbibliothek-Container, Zeichenfolgen und Arrays sind vorgefertigte für bereichsbasierte **für** Schleifen. Um diese neue Iterationssyntax für den benutzerdefinierten Typ zu aktivieren, fügen Sie die folgende Unterstützung hinzu:

- Eine `begin`-Methode, die einen Iterator zum Anfang der Struktur zurückgibt und eine `end`-Methode, die einen Iterator an das Ende der Struktur zurückgibt.

- Unterstützung im Iterator für diese Methoden: **Operator**<strong>\*</strong>, **Operator! =**, und **"Operator++"** (präfixversion).

Diese Methoden können entweder Member oder eigenständige Funktionen sein.

## <a name="random-numbers"></a>Zufallszahlen

Es ist bekannt, dass die alte Funktion CRT `rand()`-Funktion viele Fehler enthält, die ausführlich in der C++-Community erläutert wurden. In modernem C++, die Sie für den Umgang mit diese Schwachpunkt haben keine – ebenso wenig müssen Sie Ihre eigenen gleichmäßig verteilten Zufallszahlen-Generator zu erfinden, da die Tools zum schnellen und einfachen Erstellen sie in der C++-Standardbibliothek, verfügbar sind, siehe [ \<random >](../standard-library/random.md).

## <a name="see-also"></a>Siehe auch

[Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)<br/>
