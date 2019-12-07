---
title: Formatieren von Zeichenfolgen und Ein-/Ausgaben (Modern C++)
description: Optionen für formatierte Zeichen folgen-e/a C++, die in modern verfügbar sind
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: 7ea858a8a8126d3754783edee0dd3ea5409e5f73
ms.sourcegitcommit: 6ddfb8be5e5923a4d90a2c0f93f76a27ce7ac299
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2019
ms.locfileid: "74898829"
---
# <a name="string-and-io-formatting-modern-c"></a>Formatieren von Zeichenfolgen und Ein-/Ausgaben (Modern C++)

C++[\<iostream->](../standard-library/iostream.md) Klassen, Funktionen und Operatoren unterstützen formatierte Zeichen folgen-e/a. Der folgende Code zeigt beispielsweise, wie `cout` so festgelegt wird, dass eine Ganzzahl als hexadezimal Ausgabe formatiert wird. Zuerst wird der aktuelle Zustand gespeichert, um ihn anschließend zurückzusetzen, denn sobald der Formatierungs Zustand an `cout`übermittelt wird, bleibt er so lange unverändert. Dies gilt nicht nur für die einzige Codezeile.

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

Diese Vorgehensweise ist typsicher und erweiterbar, aber auch komplex und ausführlich.

## <a name="alternative-format-options"></a>Alternative Formatoptionen

Als Alternative können Sie `Boost.Format` aus den Boost C++ -Bibliotheken verwenden, auch wenn dies nicht der Standard ist. Sie können alle Boost-Bibliotheken von der [Boost](https://www.boost.org/) -Website herunterladen.

Einige Vorteile von `Boost.Format` sind:

- Safe: typsicher, und löst eine Ausnahme für Fehler aus, z. b. die Angabe von zu wenigen oder zu vielen Elementen.

- Erweiterbar: Funktioniert für jeden Typ, der gestreamt werden kann

- Praktisch: POSIX-Standard Zeichen und ähnliche Format Zeichenfolgen.

Obwohl `Boost.Format` auf C++ [\<iostream->](../standard-library/iostream-programming.md) Einrichtungen basiert, die sicher und erweiterbar sind, sind Sie nicht leistungsoptimiert. Wenn Sie eine Leistungsoptimierung benötigen, sollten Sie C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) und [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)in Erwägung nehmen, die schnell und einfach zu verwenden sind. Sie sind jedoch nicht erweiterbar oder nicht sicher vor Sicherheitsrisiken. (Sichere Versionen sind vorhanden, doch verursachen diese geringfügige Leistungseinbußen. Weitere Informationen finden Sie unter [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) und [sprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)(_sprintf_s_l, swprintf_s, _swprintf_s_l).

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

[Willkommen zurück beiC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<limits>](../standard-library/limits.md)<br/>
[\<iomanip>](../standard-library/iomanip.md)
