---
title: Compilerwarnung (Stufe 3) C4996 | Microsoft Docs
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
ms.openlocfilehash: a6af8a8ff3cde50ea8b196e7f293874998547ec0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315398"
---
# <a name="compiler-warning-level-3-c4996"></a>Compilerwarnung (Stufe 3) C4996

Der Compiler hat eine veraltete Deklaration gefunden. **Diese Warnung ist immer eine absichtliche Nachricht von der Autor der Bibliothek oder der zugehörigen Header-Datei nur die Konsequenzen sollten Sie nicht als veraltet markierte Symbol verwenden.** Die tatsächliche Warnmeldung wird durch die veraltete Modifizierer oder das Attribut am Standort der Deklaration angegeben. 

Dies sind einige allgemeine C4996 Nachrichten, die von C-Laufzeitbibliothek und der Standardbibliothek, aber nicht für eine vollständige Liste generiert. Folgen Sie den Links, oder Lesen Sie nach Möglichkeiten, um das Problem zu beheben oder die Warnung deaktivieren auf. 

- [Der POSIX-Name für dieses Element ist veraltet. Verwenden Sie stattdessen die ISO C- und C++-konformen Namen: *New_name*. Details finden Sie in der Onlinehilfe.](#posix-function-names)

- [Diese Funktion oder Variable möglicherweise unsicher. Erwägen Sie *sichere_version* stattdessen. Verwenden Sie zum Deaktivieren der veraltungswarnung \_CRT\_SECURE\_keine\_WARNUNGEN.  Details finden Sie in der Onlinehilfe.](#unsafe-crt-library-functions)

- ["std::*Function_name*::\_deaktiviert\_Iteratoren::\_Deprecate" aufrufen, um std::*Function_name*mit Parametern, die ggf. unsicher - Aufruf abhängig. der Aufrufer sicherstellen, dass die übergebenen Werte richtig sind. Sie können diese Warnung mit D_SCL_SECURE_NO_WARNINGS deaktivieren. Dokumentation zum Verwenden von Visual C++ "Überprüfte Iteratoren" finden Sie unter](#unsafe-standard-library-functions)

- [Diese Funktion oder Variable wurde durch neuere Bibliothek oder einem Betriebssystem-Funktionalität ersetzt. Erwägen Sie *neues_element* stattdessen. Details finden Sie in der Onlinehilfe.](#obsolete-crt-functions-and-variables)

## <a name="cause"></a>Ursache

C4996 tritt auf, wenn der Compiler erkennt, eine Funktion oder Variable mit der Kennzeichnung [veraltet](../../cpp/deprecated-cpp.md) mithilfe einer `__declspec(deprecated)` Modifizierer, oder wenn Sie versuchen, Zugriff auf eine Funktion, die Klassenmember oder Typedef, die die C ++ 14 hat [ \[ \[veraltet\] \] ](../../cpp/attributes.md) Attribut. Sie können die `__declspec(deprecated)` Modifizierer oder `[[deprecated]]` -Attribut selbst in den Bibliotheken oder Headerdateien, die Ihre Clients zu als veraltet markierte Funktionen, Variablen, Mitglieder oder Typdefinitionen warnt.

## <a name="remarks"></a>Hinweise

Viele Funktionen, Memberfunktionen, Vorlagenfunktionen und globale Variablen in den Bibliotheken in Visual Studio werden als *veraltet*. Diese Funktionen sind veraltet, da sie möglicherweise einen anderen, bevorzugten Name, möglicherweise unsicher aufweisen oder eine sicherere Variante oder schlicht veraltet. Viele Veraltung-Nachrichten enthalten einen Ersatz für die veraltete Funktion oder globale Variable.

Um dieses Problem zu beheben, empfehlen wir in der Regel, dass Sie den Code, um die vorgeschlagene sicherer oder aktualisierte Funktionen und globalen Variablen verwenden Sie stattdessen ändern. Wenn Sie die vorhandenen Funktionen oder Variablen aus Gründen der Portabilität verwenden müssen, kann die Warnung deaktiviert werden.

### <a name="to-turn-the-warning-off-without-fixing-the-issue"></a>Die Warnung deaktivieren, ohne das Problem beheben

Sie können die Warnung für eine bestimmte Codezeile deaktivieren, mit der [Warnung](../../preprocessor/warning.md) Pragma `#pragma warning(suppress : 4996)`. Sie können auch die Warnung in einer Datei mit deaktivieren Warning-Pragma `#pragma warning(disable : 4996)`.

Sie können die Warnung Global in Befehlszeilenbuilds über Deaktivieren der **/wd4996** -Befehlszeilenoption.

So deaktivieren Sie die Warnung für ein gesamtes Projekt in Visual Studio-IDE

- Öffnen der **Eigenschaftenseiten** -Dialogfeld für Ihr Projekt. Informationen zum Verwenden Sie des Dialogfeld "Eigenschaftenseiten" finden Sie unter [Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md).
- Wählen Sie die **Konfigurationseigenschaften**, **C/C++-**, **erweitert** Seite.
- Bearbeiten der **bestimmte Warnungen deaktivieren** hinzuzufügenden Eigenschaft `4996`. Wählen Sie **OK** um die Änderungen zu übernehmen.

Präprozessormakros können auch um bestimmte bestimmten Klassen von veraltungswarnungen verwendet, die in den Bibliotheken zu deaktivieren. Diese Makros werden nachfolgend beschrieben.

So definieren Sie ein Präprozessormakro in Visual Studio

- Öffnen der **Eigenschaftenseiten** -Dialogfeld für Ihr Projekt. Informationen zum Verwenden Sie des Dialogfeld "Eigenschaftenseiten" finden Sie unter [Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md).
- Erweitern Sie **Konfigurationseigenschaften > C/C++-> Präprozessor**.
- In der **Präprozessordefinitionen** -Eigenschaft, fügen Sie den Makronamen. Wählen Sie **OK** aus, um Ihre Änderung zu speichern, und erstellen Sie das Projekt anschließend neu.

Um ein Makro nur in bestimmten Quelldateien zu definieren, fügen Sie eine Zeile wie z. B. `#define EXAMPLE_MACRO_NAME` vor jeder Zeile, die eine Headerdatei einbindet.

## <a name="specific-c4996-messages"></a>Bestimmte C4996 Nachrichten

Hier sind einige der häufig auftretenden C4996 Warnungen und Fehler.

### <a name="posix-function-names"></a>POSIX-Funktionsnamen

**Der POSIX-Name für dieses Element ist veraltet. Verwenden Sie stattdessen die ISO C- und C++-konformen Namen:** *New_name*. **Finden Sie in der Onlinehilfe für Details.**

Microsoft hat einige POSIX-Funktionen in der CRT mit C99 und C ++ 03 festgelegten Regeln für die Implementierung definiertes globale Funktionsnamen entsprechen umbenannt. Nur die ursprünglichen POSIX-Namen sind veraltet, nicht die Funktionen selbst. In den meisten Fällen wurde dem POSIX-Funktionsnamen ein führender Unterstrich hinzugefügt, um einen mit dem Standard-konformen Namen zu erzielen. Der Compiler gibt für den ursprünglichen Funktionsnamen eine veraltungswarnung und schlägt den bevorzugten Namen vor.

Um dieses Problem zu beheben, empfehlen wir in der Regel, dass Sie den Code, um stattdessen die empfohlene Funktionsnamen ändern. Allerdings sind die aktualisierten Namen Microsoft-spezifisch. Wenn Sie die vorhandenen Funktionsnamen aus Gründen der Portabilität verwenden müssen, können Sie diese Hinweise zu deaktivieren. Die POSIX-Funktionen sind in der Bibliothek unter ihre Originalnamen weiterhin verfügbar.

Um die veraltungswarnungen für diese Funktionen zu deaktivieren, definieren Sie das Präprozessor-Makro  **\_CRT\_NONSTDC\_keine\_WARNUNGEN**. Sie können dieses Makro in der Befehlszeile durch Einschließen der Option definieren `/D_CRT_NONSTDC_NO_WARNINGS`.


### <a name="unsafe-crt-library-functions"></a>Unsichere CRT-Bibliotheksfunktionen

 **Diese Funktion oder Variable möglicherweise unsicher. Erwägen Sie** *sichere_version* **stattdessen. Verwenden Sie zum Deaktivieren der veraltungswarnung \_CRT\_SECURE\_keine\_WARNUNGEN.  Details finden Sie in der Onlinehilfe.**

 Microsoft hat einige CRT- und C++-Standardbibliothek Funktionen und globale Variablen zugunsten sicherere Versionen veraltet. In den meisten Fällen ermöglichen die als veraltet markierte Funktionen deaktiviert Lese- oder Schreibzugriff auf den Puffer zu schweren Sicherheitsproblemen führen kann. Der Compiler gibt für diese Funktionen eine Veraltungswarnung aus und schlägt die bevorzugte Funktion vor.

 Um dieses Problem zu beheben, wird empfohlen, die Funktion oder Variable *sichere_version* stattdessen. Wenn Sie überprüft haben, dass es nicht möglich, für das Überschreiben einer Puffer ist oder Overread erfolgen in Ihrem Code, und Sie den Code aus Gründen der Portabilität kann nicht geändert werden, können Sie die Warnung deaktivieren.
 
 Um die veraltungswarnungen für diese Funktionen in der CRT zu deaktivieren, definieren  **\_CRT\_SECURE\_keine\_WARNUNGEN**. Um Warnungen zu veralteten globalen Variablen zu deaktivieren, definieren  **\_CRT\_SECURE\_keine\_WARNUNGEN\_GLOBALS**. Weitere Informationen zu diesen Funktionen als veraltet markierte Funktionen und globale Variablen finden Sie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) und [sichere Bibliotheken: C++-Standardbibliothek](../../standard-library/safe-libraries-cpp-standard-library.md).

### <a name="unsafe-standard-library-functions"></a>Unsichere Standardbibliotheksfunktionen

__"std::__*Function_name*__::\_deaktiviert\_Iteratoren::\_Deprecate" aufrufen, um std::__*Function_name* **mit Parametern, die ggf. unsicher - verwendet diesen Aufruf für den Aufrufer zu überprüfen, dass die übergebenen Werte richtig sind. Um diese Warnung zu deaktivieren, verwenden Sie die D -\_SCL\_SECURE\_keine\_WARNUNGEN. Dokumentation zum Verwenden von Visual C++ "Überprüfte Iteratoren" finden Sie unter**

Diese Warnung wird in der Debug-Builds angezeigt, da bestimmte Vorlagenfunktionen der C++-Standardbibliothek nicht Parameter auf Richtigkeit überprüft werden. In den meisten Fällen ist dies, weil nicht genügend Informationen für die Funktion zum Überprüfen der Grenzen des Containers verfügbar ist oder weil Iteratoren nicht ordnungsgemäß mit der Funktion verwendet werden können. Diese Warnung können Sie diese Funktion verwendet wird, zu identifizieren, da sie eine Quelle für schwerwiegende Sicherheitslücken im Programm sein können. Weitere Informationen finden Sie unter [Checked Iterators](../../standard-library/checked-iterators.md).

Beispielsweise diese Warnung wird im Debugmodus angezeigt, wenn Sie einen Element auf eine übergeben `std::copy` anstelle eines einfachen Arrays. Um dieses Problem zu beheben, verwenden Sie ein entsprechend deklariertes Array, sodass die Bibliothek können Sie die Array-Blöcke überprüfen und führen Sie die Überprüfung von Grenzen.

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

Mehrere Algorithmen der Standardbibliothek wurden aktualisiert, um "duale Bereich" Versionen in C ++ 14 aufweisen. Wenn Sie die zwei Bereichs-Versionen verwenden, bietet der zweite Bereich erforderlichen Begrenzungen bei der Überprüfung:

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

Dieses Beispiel zeigt verschiedene weitere Möglichkeiten die Standardbibliothek kann verwendet werden, um das Iterator-Syntax zu überprüfen und wenn unchecked-Syntax kann gefährlich sein:

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

Wenn Sie überprüft haben, dass Code einen Pufferüberlauf Fehler in der Standardbibliothek-Funktionen, die diese Warnung auslösen kann, empfiehlt es sich um diese Warnung zu deaktivieren. Um Warnungen für diese Funktionen deaktivieren, definieren  **\_SCL\_SECURE\_keine\_WARNUNGEN**.

### <a name="checked-iterators-enabled"></a>Aktivierte Iteratoren aktiviert

C4996 kann auch auftreten, wenn Sie einen überprüften Iterator nicht, beim Kompilieren verwenden mit `_ITERATOR_DEBUG_LEVEL` als 1 oder 2 definiert. Es ist auf 2 wird standardmäßig im Debugmodus, und für retailbuilds auf 0 festgelegt. Weitere Informationen finden Sie unter [Checked Iterators](../../standard-library/checked-iterators.md) .

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

C4996 kann auch auftreten, wenn Sie MFC oder ATL-Funktionen, die nicht mehr implementiert wurden aus Sicherheitsgründen verwenden.

Um dieses Problem zu beheben, wird dringend empfohlen, dass Sie den Code, um stattdessen aktualisierte Funktionen ändern.

Informationen zum Unterdrücken dieser Warnungen finden Sie unter [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings).

### <a name="obsolete-crt-functions-and-variables"></a>Veraltete CRT-Funktionen und Variablen

**Diese Funktion oder Variable wurde durch neuere Bibliothek oder einem Betriebssystem-Funktionalität ersetzt. Erwägen Sie** *neues_element* **stattdessen. Details finden Sie in der Onlinehilfe.**

Einige Bibliotheksfunktionen und globale Variablen wurden als veraltet gekennzeichnet. Diese Funktionen und Variablen werden möglicherweise in einer zukünftigen Version der Bibliothek entfernt. Der Compiler gibt für diese Elemente eine Veraltungswarnung aus und schlägt die bevorzugte Alternative vor.

Um dieses Problem zu beheben, wird empfohlen, dass Sie den Code, um die vorgeschlagene Funktion oder Variable verwenden ändern.

Um die veraltungswarnungen für diese Elemente zu deaktivieren, definieren  **\_CRT\_veraltet\_keine\_WARNUNGEN**. Weitere Informationen finden Sie in der Dokumentation für die veraltete Funktion oder Variable.

### <a name="marshalling-errors-in-clr-code"></a>Marshalling von Fehlern in CLR-Code

C4996 kann auch auftreten, wenn Sie die Marshallingbibliothek CLR verwenden. In diesem Fall ist C4996 ein Fehler, keine Warnung. Dieser Fehler tritt auf, wenn Sie [Marshal_as](../../dotnet/marshal-as.md) zum Konvertieren zwischen zwei Datentypen, die erfordern einen [Marshal_context-Klasse](../../dotnet/marshal-context-class.md). Sie erhalten diesen Fehler auch, wenn die Marshallingbibliothek keine Konvertierung unterstützt. Weitere Informationen über die Marshallingbibliothek finden Sie unter [Overview of Marshaling in C++](../../dotnet/overview-of-marshaling-in-cpp.md).

In diesem Beispiel wird C4996 erzeugt, weil die Marshallingbibliothek einen Kontext zum Konvertieren von benötigt eine `System::String` zu einem `const char *`.

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

Sie können das veraltete Attribut in Ihrem eigenen Code verwenden, um Aufrufern warnen, wenn Sie bestimmte Funktionen nicht mehr empfohlen. In diesem Beispiel wird C4996 generiert, für die Zeile in der die als veraltet markierte Funktion deklariert wird, sowie für die Zeile, die auf der die Funktion verwendet wird.

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
