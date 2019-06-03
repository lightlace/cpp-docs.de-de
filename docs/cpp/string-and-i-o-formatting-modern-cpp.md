---
title: Formatieren von Zeichenfolgen und Ein-/Ausgaben (Modern C++)
description: Optionen für die formatierte Zeichenfolge verfügbaren e/a in Modern C++.
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: e22c745798109a2dbef82297c45256593823f806
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450501"
---
# <a name="string-and-io-formatting-modern-c"></a>Formatieren von Zeichenfolgen und Ein-/Ausgaben (Modern C++)

C++[ \<Iostream >](../standard-library/iostream.md) formatierte Zeichenfolge e/a-Klassen, Funktionen und Operatoren zu unterstützen. Der folgende Code zeigt z. B. festlegen `cout` so formatieren eine ganze Zahl im Hexadezimalformat ausgegeben. Speichert zunächst den aktuellen Zustand zum danach zurücksetzen, da einmal Format Zustand, um übergeben wird `cout`, es bleibt auf diese Weise bis geändert. Es gilt nicht nur für die eine Codezeile erforderlich.

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main()
{
    ios state(nullptr);

    cout << "The answer in decimal is: " << 42 << endl;

    state.copyfmt(cout); // save current formatting
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers
        << hex
        << uppercase
        << setw(8)
        << setfill('0')
        << 42            // the actual value we wanted to print out
        << endl;
    cout.copyfmt(state); // restore previous formatting
}
```

Dieser Ansatz ist, typsicher und erweiterbares, aber es ist auch komplex und ausführlich.

## <a name="alternative-format-options"></a>Alternative Formatoptionen

Als Alternative können Sie `Boost.Format` über die Verstärkung C++ Bibliotheken, auch wenn es nicht dem Standard entspricht. Sie können jede auftriebsbibliothek von der [Boost](https://www.boost.org/) Website.

Einige Vorteile von `Boost.Format` sind:

- Sicher: Typsicher und löst eine Ausnahme für Fehler, z. B. der Spezifikation zu wenige oder zu viele Elemente.

- Erweiterbar: Kann für jeden Typ, der gestreamt werden kann.

- Praktisch: Standard-Posix und ähnliche Formatzeichenfolgen.

Obwohl `Boost.Format` basiert auf C++ [ \<Iostream >](../standard-library/iostream-programming.md) Einrichtungen, die sicher und erweiterbar sind, sie aber nicht leistungsoptimiert. Wenn Sie zur Optimierung der Leistung benötigen, sollten Sie C [Printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) und [Sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), denen sind, schnell und einfach zu verwenden. Allerdings sind sie nicht erweiterbar und können Sicherheitsrisiken bergen. (Sichere Versionen sind vorhanden, doch verursachen diese geringfügige Leistungseinbußen. Weitere Informationen finden Sie unter [Printf_s, _printf_s_l, Wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) und [Sprintf_s, _sprintf_s_l, Swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)).

Im folgenden Code werden einige der Boost-Formatierungsfunktionen verdeutlicht.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>Siehe auch

[Willkommen zurück bei C++ (Modern C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<limits>](../standard-library/limits.md)<br/>
[\<iomanip>](../standard-library/iomanip.md)
