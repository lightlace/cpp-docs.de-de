---
title: Compilerwarnung (Stufe 3) C4996 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4996
dev_langs:
- C++
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d618ace9d922daabecf908c76a319e89a9fdedcc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094181"
---
# <a name="compiler-warning-level-3-c4996"></a>Compilerwarnung (Stufe 3) C4996

Der Compiler hat eine veraltete Deklaration gefunden. **Diese Warnung ist immer eine absichtliche Nachricht aus der Autor der Bibliothek oder den zugehörigen Header-Datei, die als veraltet markierte Symbol nicht verwendet sollte nur die Konsequenzen bewusst sind.** Die tatsächliche Warnmeldung wird durch die Einstellung Modifizierer oder das Attribut am Standort der Deklaration angegeben.

Dies sind einige allgemeine C4996-Nachrichten, die von C-Laufzeitbibliothek und der Standardbibliothek, aber keine vollständige Liste generiert. Folgen Sie den Links, oder Lesen Sie weiter nach Möglichkeiten, um das Problem zu beheben oder die Warnung deaktivieren.

- [Der POSIX-Name für dieses Element ist veraltet. Verwenden Sie stattdessen den ISO C- und C++-konformen Namen: *New_name*. Details finden Sie in der Onlinehilfe.](#posix-function-names)

- [Diese Funktion oder Variable möglicherweise unsicher. Erwägen Sie die Verwendung *sichere_version* stattdessen. Verwenden Sie zum Deaktivieren der veraltungswarnung \_CRT\_SECURE\_keine\_WARNUNGEN.  Details finden Sie in der Onlinehilfe.](#unsafe-crt-library-functions)

- ["std::*Function_name*::\_deaktiviert\_Iteratoren::\_Deprecate" aufrufen, um std::*Function_name*mit Parametern, die möglicherweise unsicher dieser Aufruf verwendet der Aufrufer zu überprüfen, ob die übergebenen Werte korrekt sind. Sie können diese Warnung mit D_SCL_SECURE_NO_WARNINGS deaktivieren. Finden Sie Dokumentation zur Verwendung von Visual C++ "Überprüfte Iteratoren"](#unsafe-standard-library-functions)

- [Diese Funktion oder Variable wurde durch neuere Bibliothek oder einem Betriebssystem-Funktion ersetzt. Erwägen Sie die Verwendung *neues_element* stattdessen. Details finden Sie in der Onlinehilfe.](#obsolete-crt-functions-and-variables)

## <a name="cause"></a>Ursache

C4996 tritt auf, wenn der Compiler findet, eine Funktion oder Variable mit der Kennzeichnung [veraltet](../../cpp/deprecated-cpp.md) mithilfe einer `__declspec(deprecated)` Modifizierer, oder wenn Sie versuchen, Zugriff auf eine Funktion, die Member der Klasse oder die Typedef, die die C ++ 14 [ \[ \[veraltet\] \] ](../../cpp/attributes.md) Attribut. Sie können die `__declspec(deprecated)` Modifizierer oder `[[deprecated]]` -Attribut selbst in Ihre Bibliotheken oder Headerdateien, um Ihre Clients zu als veraltet markierte Funktionen, Variablen, Member oder Typedefs zu warnen.

## <a name="remarks"></a>Hinweise

Viele Funktionen, Memberfunktionen, Vorlagenfunktionen und globale Variablen in den Bibliotheken in Visual Studio werden als *veraltet*. Diese Funktionen sind veraltet, da sie möglicherweise einen anderen Namen für die bevorzugte, möglicherweise unsicher oder eine sicherere Variante ist, oder möglicherweise veraltet. Viele der befehlshilfe enthalten ein Ersatz für die veraltete Funktion oder globale Variable.

Um dieses Problem zu beheben, empfehlen wir normalerweise, dass Sie Ihren Code, um stattdessen verwenden Sie die vorgeschlagenen sicherer oder aktualisierte Funktionen und globalen Variablen ändern. Wenn Sie die vorhandenen Funktionen oder Variablen aus Gründen der Portabilität verwenden müssen, kann die Warnung deaktiviert werden.

### <a name="to-turn-the-warning-off-without-fixing-the-issue"></a>Die Warnung deaktivieren, ohne das Problem zu beheben

Sie können die Warnung für eine bestimmte Zeile Code deaktivieren, mit der [Warnung](../../preprocessor/warning.md) Pragma `#pragma warning(suppress : 4996)`. Sie können auch deaktivieren die Warnung in einer Datei mit der Warning-Pragma `#pragma warning(disable : 4996)`.

Sie können die Warnung Global in Befehlszeilenbuilds über Deaktivieren der **/wd4996** -Befehlszeilenoption.

So deaktivieren die Warnung für ein gesamtes Projekt in Visual Studio-IDE:

- Öffnen der **Eigenschaftenseiten** -Dialogfeld für Ihr Projekt. Informationen zur Verwendung der Eigenschaftenseiten (Dialogfeld), finden Sie unter [Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md).
- Wählen Sie die **Konfigurationseigenschaften**, **C/C++-**, **erweitert** Seite.
- Bearbeiten der **bestimmte Warnungen deaktivieren** hinzuzufügende Eigenschaft `4996`. Wählen Sie **OK** zum Übernehmen der Änderungen.

Sie können Präprozessormakros auch verwenden, deaktivieren Sie bestimmte bestimmten Klassen von veraltungswarnungen, die in den Bibliotheken verwendet. Diese Makros werden nachfolgend beschrieben.

So definieren Sie eine Präprozessor-Makro in Visual Studio

- Öffnen der **Eigenschaftenseiten** -Dialogfeld für Ihr Projekt. Informationen zur Verwendung der Eigenschaftenseiten (Dialogfeld), finden Sie unter [Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md).
- Erweitern Sie **Konfigurationseigenschaften > C/C++ > Präprozessor**.
- In der **Präprozessordefinitionen** -Eigenschaft, fügen Sie den Makronamen. Wählen Sie **OK** aus, um Ihre Änderung zu speichern, und erstellen Sie das Projekt anschließend neu.

Fügen Sie ein Makro nur in bestimmten Quelldateien zu definieren, eine Zeile ein, z. B. `#define EXAMPLE_MACRO_NAME` vor jeder Zeile, die eine Headerdatei umfasst.

## <a name="specific-c4996-messages"></a>Bestimmte C4996 Nachrichten

Hier sind einige der häufige Fehlerquellen C4996 Warnungen und Fehler.

### <a name="posix-function-names"></a>POSIX-Funktionsnamen

**Der POSIX-Name für dieses Element ist veraltet. Verwenden Sie stattdessen den ISO C- und C++-konformen Namen:** *New_name*. **Finden Sie in der Onlinehilfe für Details.**

Microsoft hat einige POSIX-Funktionen in der CRT mit C99 und C ++ 03 festgelegten Regeln für die Implementierung definierten globalen Funktionsnamen entsprechen umbenannt. Nur die ursprünglichen POSIX-Namen sind veraltet, nicht die Funktionen selbst. In den meisten Fällen wurde dem POSIX-Funktionsnamen ein führender Unterstrich hinzugefügt, um einen mit dem Standard-konformen Namen zu erzielen. Der Compiler gibt für den ursprünglichen Funktionsnamen eine veraltungswarnung aus, und schlägt den bevorzugten Namen vor.

Um dieses Problem zu beheben, empfehlen wir normalerweise, dass Sie Ihren Code, um stattdessen die empfohlene Funktionsnamen ändern. Allerdings sind die Namen die aktualisierten Microsoft-spezifisch. Wenn Sie den Namen der vorhandenen Funktionen aus Gründen der Portabilität verwenden müssen, können Sie diese Warnungen deaktivieren. POSIX-Funktionen stehen immer noch in der Bibliothek unter deren ursprünglichen Namen.

Um die veraltungswarnungen für diese Funktionen zu deaktivieren, definieren Sie das Präprozessor-Makro  **\_CRT\_NONSTDC\_keine\_WARNUNGEN**. Sie können dieses Makro in der Befehlszeile durch Einschließen der Option definieren `/D_CRT_NONSTDC_NO_WARNINGS`.


### <a name="unsafe-crt-library-functions"></a>Unsichere Funktionen der CRT-Bibliothek

**Diese Funktion oder Variable möglicherweise unsicher. Erwägen Sie die Verwendung** *sichere_version* **stattdessen. Verwenden Sie zum Deaktivieren der veraltungswarnung \_CRT\_SECURE\_keine\_WARNUNGEN.  Details finden Sie in der Onlinehilfe.**

Microsoft hat einige CRT- und C++-Standardbibliothek-Funktionen und globale Variablen und sicherere Versionen veraltet. In den meisten Fällen können die als veraltet markierte Funktionen deaktiviert Lese- oder Schreibzugriff auf den Ausgabepuffern, die zu schwerwiegenden Sicherheitsproblemen führen können. Der Compiler gibt für diese Funktionen eine Veraltungswarnung aus und schlägt die bevorzugte Funktion vor.

Um dieses Problem zu beheben, sollten Sie die Funktion oder Variable *sichere_version* stattdessen. Wenn Sie überprüft haben, dass es nicht möglich, für das Überschreiben einer Puffer ist oder Overread erfolgen in Ihrem Code, und Sie den Code aus Gründen der Portabilität kann nicht geändert werden, können Sie die Warnung deaktivieren.

Um die veraltungswarnungen für diese Funktionen in der CRT zu deaktivieren, definieren  **\_CRT\_SECURE\_keine\_WARNUNGEN**. Um die Warnungen zu veralteten globalen Variablen zu deaktivieren, definieren  **\_CRT\_SECURE\_keine\_WARNUNGEN\_GLOBALS**. Weitere Informationen über diese veralteten Funktionen und globale Variablen, finden Sie unter [Sicherheitsfunktionen in CRT](../../c-runtime-library/security-features-in-the-crt.md) und [sichere Bibliotheken: C++-Standardbibliothek](../../standard-library/safe-libraries-cpp-standard-library.md).

### <a name="unsafe-standard-library-functions"></a>Unsichere Funktionen der Standard-Bibliothek

__"std::__*Function_name*__::\_deaktiviert\_Iteratoren::\_Deprecate" aufrufen, um std::__*Function_name* **mit Parametern, die möglicherweise unsicher verwendet diesen Aufruf dem Aufrufer, überprüfen Sie, dass die übergebenen Werte korrekt sind. Um diese Warnung zu deaktivieren, verwenden Sie -D\_SCL\_SECURE\_keine\_WARNUNGEN. Finden Sie Dokumentation zur Verwendung von Visual C++ "Überprüfte Iteratoren"**

Diese Warnung wird in der Debug-Builds angezeigt, da bestimmte Vorlagenfunktionen der C++-Standardbibliothek nicht Parameter für die Richtigkeit überprüfen. In den meisten Fällen ist dies, da nicht genügend Informationen für die Funktion zum Überprüfen der Grenzen des Containers verfügbar ist oder weil Iteratoren nicht ordnungsgemäß mit der Funktion verwendet werden können. Anhand dieser Warnung können Sie diese Funktion verwendet, zu identifizieren, da sie eine Quelle für schwerwiegende Sicherheitslücken im Programm möglicherweise. Weitere Informationen finden Sie unter [Checked Iterators](../../standard-library/checked-iterators.md).

Beispielsweise diese Warnung wird im Debugmodus angezeigt, wenn Sie einen Elementzeiger, übergeben `std::copy` anstelle eines einfachen Arrays. Um dieses Problem zu beheben, verwenden Sie ein entsprechend deklariertes Array ist, damit die Bibliothek können Sie die Array-Blöcke überprüfen und führen die Überprüfung der Begrenzungen.

```cpp
// C4996_copyarray.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_copyarray.cpp
#include <algorithm>

void example(char const * const src) {
    char dest[1234];
    char * pdest3 = dest + 3;
    std::copy(src, src + 42, pdest3); // C4996
    std::copy(src, src + 42, dest);   // OK, copy can tell that dest is 1234 elements
}
```

Mehrere Algorithmen der Standardbibliothek wurden aktualisiert, um "dual-Bereich"-Versionen in C ++ 14 aufweisen. Wenn Sie die zwei Bereichs-Versionen verwenden, stellt der zweite Bereich erforderlichen Begrenzungen bei der Überprüfung:

```cpp
// C4996_containers.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_containers.cpp
#include <algorithm>

bool example(
    char const * const left,
    const size_t leftSize,
    char const * const right,
    const size_t rightSize)
{
    bool result = false;
    result = std::equal(left, left + leftSize, right); // C4996
    // To fix, try this form instead:
    // result = std::equal(left, left + leftSize, right, right + rightSize); // OK
    return result;
}
```

Dieses Beispiel zeigt verschiedene weitere Möglichkeiten, die möglicherweise die Standardbibliothek verwendet werden, um die Iterator-Syntax zu überprüfen und wann deaktiviert Nutzung kann gefährlich sein:

```cpp
// C4996_standard.cpp
// compile with: cl /EHsc /W4 /MDd C4996_standard.cpp
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
    // (i.e. an overrun triggers a debug assertion)
    vector<int> v2(16);
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });
    print("v2: ", v2);

    // OK: back_insert_iterator is marked as checked in debug mode
    // (i.e. an overrun is impossible)
    vector<int> v3;
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });
    print("v3: ", v3);

    // OK: array::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    array<int, 16> a4;
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });
    print("a4: ", a4);

    // OK: Raw arrays are checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    // NOTE: This applies only when raw arrays are
    // given to C++ Standard Library algorithms!
    int a5[16];
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });
    print("a5: ", a5);

    // WARNING C4996: Pointers cannot be checked in debug mode
    // (i.e. an overrun triggers undefined behavior)
    int a6[16];
    int * p6 = a6;
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });
    print("a6: ", a6);

    // OK: stdext::checked_array_iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    int a7[16];
    int * p7 = a7;
    transform(v.begin(), v.end(),
        stdext::make_checked_array_iterator(p7, 16),
        [](int n) { return n * 7; });
    print("a7: ", a7);

    // WARNING SILENCED: stdext::unchecked_array_iterator
    // is marked as checked in debug mode, but it performs no checking,
    // so an overrun triggers undefined behavior
    int a8[16];
    int * p8 = a8;
    transform( v.begin(), v.end(),
        stdext::make_unchecked_array_iterator(p8),
        [](int n) { return n * 8; });
    print("a8: ", a8);
}
```

Wenn Sie überprüft haben, dass Ihr Code kein Pufferüberlaufs Fehler in den Funktionen der Standard-Bibliothek, die diese Warnung auslösen, empfiehlt es sich um diese Warnung zu deaktivieren. Um die Warnungen für diese Funktionen zu deaktivieren, definieren  **\_SCL\_SECURE\_keine\_WARNUNGEN**.

### <a name="checked-iterators-enabled"></a>Überprüfte Iteratoren aktiviert

C4996 kann auch auftreten, wenn Sie einen überprüften Iterator nicht, beim Kompilieren verwenden mit `_ITERATOR_DEBUG_LEVEL` als 1 oder 2 definiert. Es ist 2 in der Standardeinstellung für Debugbuilds-Modus und für die Verkaufsversionen auf 0 festgelegt. Weitere Informationen finden Sie unter [Checked Iterators](../../standard-library/checked-iterators.md) .

```cpp
// C4996_checked.cpp
// compile with: /EHsc /W4 /MDd C4996_checked.cpp
#define _ITERATOR_DEBUG_LEVEL 2

#include <algorithm>
#include <iterator>

using namespace std;
using namespace stdext;

int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 10, 11, 12 };
    copy(a, a + 3, b + 1);   // C4996
    // try the following line instead:
    // copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK
}
```

### <a name="unsafe-mfc-or-atl-code"></a>Unsichere MFC- oder ATL-code

C4996 kann auch auftreten, wenn Sie MFC oder ATL-Funktionen, die als veraltet markiert wurden aus Gründen der Sicherheit verwenden.

Es wird dringend empfohlen, dass Sie Ihren Code, um stattdessen aktualisierte Funktionen ändern, um dieses Problem zu beheben.

Informationen zum Unterdrücken dieser Warnungen finden Sie unter [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings).

### <a name="obsolete-crt-functions-and-variables"></a>Veraltete CRT-Funktionen und Variablen

**Diese Funktion oder Variable wurde durch neuere Bibliothek oder einem Betriebssystem-Funktion ersetzt. Erwägen Sie die Verwendung** *neues_element* **stattdessen. Details finden Sie in der Onlinehilfe.**

Einige Bibliotheksfunktionen und globale Variablen wurden als veraltet gekennzeichnet. Diese Funktionen und Variablen werden möglicherweise in einer zukünftigen Version der Bibliothek entfernt. Der Compiler gibt für diese Elemente eine Veraltungswarnung aus und schlägt die bevorzugte Alternative vor.

Um dieses Problem zu beheben, empfehlen wir, dass Sie Ihren Code, um die vorgeschlagenen Funktion oder Variable verwenden, ändern.

Um die veraltungswarnungen für diese Elemente zu deaktivieren, definieren  **\_CRT\_veraltet\_keine\_WARNUNGEN**. Weitere Informationen finden Sie in der Dokumentation für die veraltete Funktion oder Variable.

### <a name="marshalling-errors-in-clr-code"></a>Marshalling von Fehlern in CLR-Code

C4996 kann auch auftreten, wenn Sie die Marshallingbibliothek CLR verwenden. In diesem Fall ist C4996 ein Fehler, keine Warnung. Dieser Fehler tritt auf, wenn Sie [Marshal_as](../../dotnet/marshal-as.md) zwischen zwei Datentypen zu konvertieren, die erfordern einen [Marshal_context-Klasse](../../dotnet/marshal-context-class.md). Sie können auch diesen Fehler erhalten, wenn die Marshallingbibliothek eine Konvertierung nicht unterstützt. Weitere Informationen über die Marshallingbibliothek finden Sie unter [Overview of Marshaling in C++](../../dotnet/overview-of-marshaling-in-cpp.md).

In diesem Beispiel wird C4996 generiert, weil die Marshallingbibliothek einen Kontext zum Konvertieren von erfordert einen `System::String` zu einem `const char *`.

```cpp
// C4996_Marshal.cpp
// compile with: /clr
// C4996 expected
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = marshal_as<const char*>( message );
   return 0;
}
```

## <a name="example-user-defined-deprecated-function"></a>Beispiel: Eine benutzerdefinierte als veraltet markierte Funktion

Sie können das veraltete Attribut in Ihrem eigenen Code verwenden, um Aufrufer zu warnen, wenn Sie bestimmte Funktionen nicht mehr wird empfohlen. In diesem Beispiel wird C4996 generiert, für die Zeile, in dem die veraltete Funktion deklariert ist und für die Zeile, die auf der die Funktion verwendet wird.

```cpp
// C4996.cpp
// compile with: /W3
// C4996 warning expected
#include <stdio.h>

// #pragma warning(disable : 4996)
void func1(void) {
   printf_s("\nIn func1");
}

__declspec(deprecated) void func1(int) {
   printf_s("\nIn func2");
}

int main() {
   func1();
   func1(1);    // C4996
}
```
