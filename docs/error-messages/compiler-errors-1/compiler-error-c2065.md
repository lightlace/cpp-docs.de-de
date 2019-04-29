---
title: Compilerfehler C2065
ms.date: 09/01/2017
f1_keywords:
- C2065
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
ms.openlocfilehash: 3daf2cd532cd07225b822c80b46fc28274d4e2a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408614"
---
# <a name="compiler-error-c2065"></a>Compilerfehler C2065

> "*Bezeichner*": nichtdeklarierter Bezeichner

Der Compiler die Deklaration für einen Bezeichner nicht gefunden werden. Es gibt viele mögliche Ursachen für diesen Fehler. Die häufigsten Ursachen für C2065 generiert werden, dass der Bezeichner wurde nicht deklariert wurde, der Bezeichner ist falsch geschrieben, der Header, in dem der Bezeichner deklariert wird, nicht in der Datei enthalten ist oder der Bezeichner einen Scope-Qualifizierer, z. B. fehlt `cout` anstelle von `std::cout`. Weitere Informationen zu den Deklarationen in C++, finden Sie unter [Deklarationen und Definitionen (C++)](../../cpp/declarations-and-definitions-cpp.md).

Hier sind einige häufig auftretende Probleme und Lösungen genauer an.

## <a name="the-identifier-is-undeclared"></a>Der Bezeichner wurde nicht deklariert

Ist der Bezeichner einer Variablen oder einem Funktionsnamen, müssen Sie sie deklarieren, bevor sie verwendet werden kann. Eine Funktionsdeklaration muss auch die Typen ihrer Parameter enthalten, bevor die Funktion verwendet werden kann. Wenn die Variable deklariert wird mit `auto`, der Compiler muss in der Lage, den Typ aus ihrem Initialisierer abzuleiten.

Wenn der Bezeichner ein Mitglied aus einer Klasse oder Struktur ist oder in einem Namespace deklariert, müssen sie anhand des Namens der Klasse oder Struktur oder dem Namespacenamen, gekennzeichnet werden, wenn außerhalb des Bereichs-Struktur, Klasse oder Namespace verwendet. Auch der Namespace muss eingebunden werden durch eine `using` wie z. B. die Richtlinie `using namespace std;`, oder der Namen des Members muss eingebunden werden durch eine `using` Deklaration, wie z. B. `using std::string;`. Andernfalls gilt der nicht qualifizierte Name einen nicht deklarierten Bezeichner im aktuellen Bereich sein.

Wenn der Bezeichner das Tag für einen benutzerdefinierten Typ, z. B. eine `class` oder `struct`, der Typ des Tags muss deklariert werden, bevor sie verwendet werden kann. Z. B. die Deklaration `struct SomeStruct { /*...*/ };` muss vorhanden sein, bevor Sie eine Variable deklarieren können `SomeStruct myStruct;` in Ihrem Code.

Wenn der Bezeichner ein Typalias ist, muss der Typ deklariert werden, mithilfe einer `using` Deklaration oder `typedef` , bevor sie verwendet werden kann. Beispielsweise müssen Sie deklarieren `using my_flags = std::ios_base::fmtflags;` vor der Verwendung `my_flags` als ein Typalias für `std::ios_base::fmtflags`.

## <a name="example-misspelled-identifier"></a>Beispiel: falsch geschriebenes Bezeichner

Dieser Fehler tritt häufig auf, wenn der Bezeichnername falsch geschrieben ist oder der Bezeichner wird, die falschen Groß- und Kleinschreibung der Buchstaben verwendet. Der Name in der Deklaration muss genau mit dem Namen entsprechen, die, den Sie verwenden.

```cpp
// C2065_spell.cpp
// compile with: cl /EHsc C2065_spell.cpp
#include <iostream>
using namespace std;
int main() {
    int someIdentifier = 42;
    cout << "Some Identifier: " << SomeIdentifier << endl;
    // C2065: 'SomeIdentifier': undeclared identifier
    // To fix, correct the spelling:
    // cout << "Some Identifier: " << someIdentifier << endl;
}
```

## <a name="example-use-an-unscoped-identifier"></a>Beispiel: Verwenden Sie einen ohne bereichseinschränkung Bezeichner

Dieser Fehler kann auftreten, wenn Ihre ID nicht ordnungsgemäß festgelegt ist. Wenn C2065 generiert, dort bei der Verwendung `cout`, dies ist die Ursache. Beim C++-Standardbibliothek-Funktionen und Operatoren werden nicht vollqualifiziert durch den Namespace, oder Sie haben nicht geschaltet der `std` Namespace in den aktuellen Bereich mithilfe einer `using` -Anweisung vom Compiler nicht gefunden werden. Um dieses Problem zu beheben, müssen Sie vollständig qualifizierte Bezeichnernamen, oder geben Sie den Namespace mit dem `using` Richtlinie.

In diesem Beispiel wird nicht kompiliert, da `cout` und `endl` werden definiert, der `std` Namespace:

```cpp
// C2065_scope.cpp
// compile with: cl /EHsc C2065_scope.cpp
#include <iostream>
// using namespace std;   // Uncomment this line to fix

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead
    std::cout << "Hello" << std::endl;
}
```

Bezeichner, die innerhalb des deklariert werden `class`, `struct`, oder `enum class` Typen müssen auch durch den Namen des von ihrem umschließenden Bereich qualifiziert werden, bei der Verwendung außerhalb dieses Bereichs.

## <a name="example-precompiled-header-isnt-first"></a>Beispiel: vorkompilierter Header nicht erste

Dieser Fehler kann auftreten, wenn Sie Präprozessordirektiven, z. B. put #include, #define oder #pragma, bevor die #include-Anweisung der vorkompilierten Headerdatei. Wenn Ihre Quelldatei eine vorkompilierte Headerdatei verwendet (d. h., wenn sie mithilfe von kompiliert wird die **"/ Yu"** -Compileroption), werden alle Präprozessordirektiven, bevor Sie die vorkompilierte Headerdatei ignoriert werden.

In diesem Beispiel wird nicht kompiliert, da `cout` und `endl` werden definiert, der \<Iostream >-Header, der ignoriert wird, da es, bevor Sie die vorkompilierte Headerdatei enthalten ist. In diesem Beispiel erstellen, erstellen Sie alle drei Dateien, und klicken Sie dann "stdafx.cpp" zu kompilieren und dann C2065_pch.cpp zu kompilieren.

```cpp
// stdafx.h
#include <stdio.h>
```

```cpp
// stdafx.cpp
// Compile by using: cl /EHsc /W4 /c /Ycstdafx.h stdafx.cpp
#include <stdafx.h>
```

```cpp
// C2065_pch.cpp
// compile with: cl /EHsc /W4 /Yustdafx.h C2065_pch.cpp
#include <iostream>
#include "stdafx.h"
using namespace std;

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
}
```

Um dieses Problem zu beheben, fügen die #include-Anweisung der \<Iostream > in der vorkompilierten Headerdatei, oder verschieben Sie ihn nach dem vorkompilierten Headerdatei in der Quelldatei enthalten ist.

## <a name="example-missing-header-file"></a>Beispiel: fehlende Headerdatei.

Sie haben nicht die Header-Datei enthalten, die den Bezeichner deklariert. Stellen Sie sicher, dass die Datei, die die Deklaration für den Bezeichner enthält in jeder Quelldatei enthalten ist, der verwendet wird.

```cpp
// C2065_header.cpp
// compile with: cl /EHsc C2065_header.cpp

//#include <stdio.h>
int main() {
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined
}
```

Eine weitere mögliche Ursache ist, wenn Sie eine Initialisiererliste ohne Verwenden der \<Initializer_list > Header.

```cpp
// C2065_initializer.cpp
// compile with: cl /EHsc C2065_initializer.cpp

// #include <initializer_list>
int main() {
    for (auto strList : {"hello", "world"})
        if (strList == "hello") // C2065: 'strList': undeclared identifier
            return 1;
    // To fix, uncomment the #include <initializer_list> line
}
```

Dieser Fehler in den Quelldateien für Windows Desktop-app möglicherweise angezeigt werden, wenn Sie definieren `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN`, oder `WIN32_EXTRA_LEAN`. Diesen Präprozessormakros ausschließen einige Headerdateien aus windows.h und Afxv\_kompiliert w32.h, zu beschleunigen. Suchen Sie in windows.h und afxv_w32.h auf eine aktuelle Beschreibung der ausgeschlossenen.

## <a name="example-missing-closing-quote"></a>Beispiel: Fehlendes schließendes Anführungszeichen

Dieser Fehler kann auftreten, wenn Sie ein schließendes Anführungszeichen hinter einer Zeichenfolgenkonstante fehlen. Dies ist eine einfache Möglichkeit, die den Compiler verwechselt werden. Beachten Sie, dass schließendes Anführungszeichen fehlen einige Zeilen vor den gemeldeten Fehler Speicherort sein kann.

```cpp
// C2065_quote.cpp
// compile with: cl /EHsc C2065_quote.cpp
#include <iostream>

int main() {
    // Fix this issue by adding the closing quote to "Aaaa"
    char * first = "Aaaa, * last = "Zeee";
    std::cout << "Name: " << first
        << " " << last << std::endl; // C2065: 'last': undeclared identifier
}
```

## <a name="example-use-iterator-outside-for-loop-scope"></a>Beispiel: Verwenden der Iterator außerhalb for-Schleifenbereich

Dieser Fehler kann auftreten, wenn Sie eine Iteratorvariable in deklarieren eine `for` Schleife, und anschließend versuchen, diese Iteratorvariable außerhalb des Bereichs der Verwendung der `for` Schleife. Der Compiler kann die [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) -Compileroption in der Standardeinstellung. Finden Sie unter [Unterstützung für Iteratordebugging](../../standard-library/debug-iterator-support.md) für Weitere Informationen.

```cpp
// C2065_iter.cpp
// compile with: cl /EHsc C2065_iter.cpp
#include <iostream>
#include <string>

int main() {
    // char last = '!';
    std::string letters{ "ABCDEFGHIJKLMNOPQRSTUVWXYZ" };
    for (const char& c : letters) {
        if ('Q' == c) {
            std::cout << "Found Q!" << std::endl;
        }
        // last = c;
    }
    std::cout << "Last letter was " << c << std::endl; // C2065
    // Fix by using a variable declared in an outer scope.
    // Uncomment the lines that declare and use 'last' for an example.
    // std::cout << "Last letter was " << last << std::endl; // C2065
}
```

## <a name="example-preprocessor-removed-declaration"></a>Beispiel: Präprozessor entfernt-Deklaration

Dieser Fehler kann auftreten, wenn Sie verweisen auf eine Funktion oder Variable, die bedingt kompiliertem Code wird, die nicht für die aktuelle Konfiguration kompiliert wird. Dies kann auch auftreten, wenn Sie eine Funktion in einer Headerdatei aufrufen, die derzeit in der aktuellen Buildumgebung nicht unterstützt wird. Wenn bestimmte Variablen oder Funktionen nur verfügbar sind, wenn ein bestimmtes Präprozessormakro definiert ist, stellen Sie sicher, dass der Code, der diese Funktionen aufgerufen nur kompiliert werden kann, wenn das gleiche Präprozessor-Makro definiert ist. Dieses Problem ist einfach zu erkennen, in der IDE, da die Deklaration für die Funktion ausgegraut ist, wenn die erforderlichen Präprozessormakros für die aktuelle Buildkonfiguration nicht definiert sind.

Dies ist ein Beispiel für Code, der funktioniert, wenn Sie im Debugmodus zu erstellen, aber nicht zur Einzelhandelsanalyse:

```cpp
// C2065_defined.cpp
// Compile with: cl /EHsc /W4 /MT C2065_defined.cpp
#include <iostream>
#include <crtdbg.h>
#ifdef _DEBUG
    _CrtMemState oldstate;
#endif
int main() {
    _CrtMemDumpStatistics(&oldstate);
    std::cout << "Total count " << oldstate.lTotalCount; // C2065
    // Fix by guarding references the same way as the declaration:
    // #ifdef _DEBUG
    //    std::cout << "Total count " << oldstate.lTotalCount;
    // #endif
}
```

## <a name="example-ccli-type-deduction-failure"></a>Beispiel: C++ / CLI-Typ Abzug Fehler

Dieser Fehler kann auftreten, wenn eine generische Funktion aufrufen, wenn das geplante Typargument nicht von den verwendeten Parametern abgeleitet werden kann. Weitere Informationen finden Sie unter [generische Funktionen (C++ / CLI)](../../extensions/generic-functions-cpp-cli.md).

```cpp
// C2065_b.cpp
// compile with: cl /clr C2065_b.cpp
generic <typename ItemType>
void G(int i) {}

int main() {
   // global generic function call
   G<T>(10);     // C2065
   G<int>(10);   // OK - fix with a specific type argument
}
```

## <a name="example-ccli-attribute-parameters"></a>Beispiel: C++ / CLI Zuordnen von Parametern

Dieser Fehler kann außerdem infolge einer Konformitätsverbesserung für Compiler für Visual C++ 2005 auftreten, und zwar beim Überprüfen der Parameter für Visual C++-Attribute.

```cpp
// C2065_attributes.cpp
// compile with: cl /c /clr C2065_attributes.cpp
[module(DLL, name=MyLibrary)];   // C2065
// try the following line instead
// [module(dll, name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```
