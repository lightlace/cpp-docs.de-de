---
title: Übersicht über den experimentellen MSVC-Präprozessor
description: Der MSVC-Präprozessor wird in Übereinstimmung mit C/C++ Standards aktualisiert.
ms.date: 11/06/2019
helpviewer_keywords:
- preprocessor, experimental
ms.openlocfilehash: 446603b34d9309c256afba9abd7234ae2ab16f5c
ms.sourcegitcommit: 2362d15b5eb18d27773c3f7522da3d0eed9e2571
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73797187"
---
# <a name="msvc-experimental-preprocessor-overview"></a>Übersicht über den experimentellen MSVC-Präprozessor

Der Microsoft C++ -Präprozessor wird zurzeit aktualisiert, um die Einhaltung von Standards zu verbessern, langjährige Fehler zu beheben und einige Verhalten zu ändern, die offiziell nicht definiert sind. Außerdem wurden neue Diagnosen hinzugefügt, um bei Fehlern in Makro Definitionen zu warnen.

Diese Änderungen in Ihrem aktuellen Zustand sind verfügbar, indem Sie den [/experimental: Preprocessor](../build/reference/experimental-preprocessor.md) -Compilerschalter in Visual Studio 2017 oder Visual Studio 2019 verwenden. Das standardmäßige präprozessorverhalten bleibt mit dem in früheren Versionen identisch.

## <a name="new-predefined-macro"></a>Neues vordefiniertes Makro

Sie können erkennen, welcher Präprozessor zum Zeitpunkt der Kompilierung verwendet wird. Überprüfen Sie den Wert des vordefinierten Makros [\_MSVC\_herkömmlichen](predefined-macros.md) , um zu ermitteln, ob der herkömmliche Präprozessor bereits verwendet wird. Dieses Makro wird von Versionen des Compilers, die es unterstützen, bedingungslos festgelegt, unabhängig davon, welcher Präprozessor aufgerufen wird. Der Wert für den herkömmlichen Präprozessor ist 1. Der Wert 0 für den konformen experimentellen Präprozessor:

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

## <a name="behavior-changes-in-the-experimental-preprocessor"></a>Verhaltensänderungen im experimentellen Präprozessor

Der erste Aufwand für den experimentellen Präprozessor lag darin, dass alle Makro Erweiterungen konform waren, damit der MSVC-Compiler mit Bibliotheken verwendet werden kann, die zurzeit aufgrund von herkömmlichem Verhalten blockiert werden. Im folgenden finden Sie eine Liste mit den gängigeren wichtigen Änderungen, die beim Testen des aktualisierten Präprozessors mit realen Projekten ausgeführt wurden.

### <a name="macro-comments"></a>Makro Kommentare

Der herkömmliche Präprozessor basiert auf Zeichen Puffern anstelle von Präprozessortoken. Dies ermöglicht ungewöhnliche Verhaltensweisen, wie z. b. den folgenden präprozessorkommentartrick, der unter dem entsprechenden Präprozessor nicht funktioniert:

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
DISAPPEARING_TYPE myVal;
```

Die standardkonforme Lösung besteht darin, `int myVal` in den entsprechenden `#ifdef/#endif` Direktiven zu deklarieren:

```cpp
#define MYVAL 1

#ifdef MYVAL
int myVal;
#endif
```

### <a name="lval"></a>L # Val

Der herkömmliche Präprozessor kombiniert fälschlicherweise ein Zeichen folgen Präfix mit dem Ergebnis des Zeichen folgen Operator [(#)](stringizing-operator-hash.md) :

```cpp
 #define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

In diesem Fall ist das `L` Präfix unnötig, da die angrenzenden Zeichenfolgenliterale nach der Makro Erweiterung immer kombiniert werden. Die abwärts kompatible Lösung besteht darin, die Definition wie folgt zu ändern:

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

Das gleiche Problem ist auch bei der Handhabung von Makros zu finden, die das Argument für ein breites Zeichenfolgenliteralzeichen "stringisieren":

```cpp
 // The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str
```

Sie können das Problem auf verschiedene Arten beheben:

- Verwenden Sie die Zeichen folgen Verkettung von `L""` und `#str`, um Präfix hinzuzufügen. Dies funktioniert, da benachbarte Zeichen folgen Literale nach der Makro Erweiterung kombiniert werden:

   ```cpp
   #define STRING1(str) L""#str
   ```

- Präfix hinzufügen, nachdem `#str` mit zusätzlicher Makro Erweiterung stringisiert wurde

   ```cpp
   #define WIDE(str) L##str
   #define STRING2(str) WIDE(#str)
   ```

- Verwenden Sie den Verkettungs Operator `##`, um die Token zu kombinieren. Die Reihenfolge der Vorgänge für "`##`" und "`#`" ist nicht angegeben, obwohl alle Compiler den `#` Operator vor `##` in diesem Fall auswerten.

   ```cpp
   #define STRING3(str) L## #str
   ```

### <a name="warning-on-invalid-"></a>Warnung bei ungültigem \#\#

Wenn der [tokeneinfügenden Operator (# #)](token-pasting-operator-hash-hash.md) nicht zu einem einzelnen gültigen Vorverarbeitungs Token führt, ist das Verhalten nicht definiert. Der herkömmliche Präprozessor kann die Token nicht kombinieren. Der neue Präprozessor entspricht dem Verhalten der meisten anderen Compiler und gibt eine Diagnose aus.

```cpp
// The ## is unnecessary and does not result in a single preprocessing token.
#define ADD_STD(x) std::##x
// Declare a std::string
ADD_STD(string) s;
```

### <a name="comma-elision-in-variadic-macros"></a>Komma-elisions in Variadic-Makros

Der herkömmliche MSVC-Präprozessor entfernt vor leeren `__VA_ARGS__` Ersetzungen immer Kommas. Der experimentelle Präprozessor folgt genauer an das Verhalten anderer beliebter plattformübergreifender Compiler. Damit das Komma entfernt wird, muss das Variadic-Argument fehlen (nicht nur leer), und es muss mit einem `##` Operator gekennzeichnet werden. Betrachten Sie das folgende Beispiel:

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // In the traditional preprocessor, the following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor will replace the following macro with: func(1, ), which will result in a syntax error.
    FUNC(1, );
}
```

Im folgenden Beispiel fehlt im-`FUNC2(1)` das Variadic-Argument in dem zu evogenden Makro. Im `FUNC2(1, )` wird das Variadic-Argument leer, aber nicht fehlt (Beachten Sie das Komma in der Argumentliste).

```cpp
#define FUNC2(a, ...) func(a , ## __VA_ARGS__)
int main()
{
   // Expands to func(1)
   FUNC2(1);

   // Expands to func(1, )
   FUNC2(1, );
}
```

Im bevorstehenden C + + 2A-Standard wurde dieses Problem durch Hinzufügen von `__VA_OPT__`behoben, das noch nicht implementiert wurde.

### <a name="macro-arguments-are-unpacked"></a>Makro Argumente werden "entpackt"

Wenn ein Makro im herkömmlichen Präprozessor eines seiner Argumente an ein anderes abhängiges Makro weiterleitet, wird das Argument beim Ersetzen nicht "entpackt". Diese Optimierung wird normalerweise nicht bemerkt, kann jedoch zu ungewöhnlichen Verhalten führen:

```cpp
// Create a string out of the first argument, and the rest of the arguments.
#define TWO_STRINGS( first, ... ) #first, #__VA_ARGS__
#define A( ... ) TWO_STRINGS(__VA_ARGS__)
const char* c[2] = { A(1, 2) };

// Conformant preprocessor results:
// const char c[2] = { "1", "2" };

// Traditional preprocessor results, all arguments are in the first string:
// const char c[2] = { "1, 2", };
```

Beim Erweitern von `A()`leitet der herkömmliche Präprozessor alle in `__VA_ARGS__` verpackten Argumente an das erste Argument von TWO_STRINGS weiter, wodurch das Variadic-Argument `TWO_STRINGS` leer bleibt. Dies bewirkt, dass das Ergebnis von `#first` "1, 2" und nicht nur "1" ist. Wenn Sie genau darauf folgen, Fragen Sie sich vielleicht, was mit dem Ergebnis der `#__VA_ARGS__` in der herkömmlichen PräprozessorErweiterung passiert ist: Wenn der Variadic-Parameter leer ist, sollte er zu einem leeren Zeichenfolgenliteral`""`führen. Aufgrund eines separaten Problems wurde das leere zeichenfolgenliteraltoken nicht generiert.

### <a name="rescanning-replacement-list-for-macros"></a>Die Ersetzungs Liste für Makros wird neu berechnet.

Nachdem ein-Makro ersetzt wurde, werden die resultierenden Token für zusätzliche Makro Bezeichner, die ersetzt werden müssen, erneut gescannt. Der Algorithmus, der vom herkömmlichen Präprozessor für die erneute Überprüfung verwendet wird, ist nicht konform, wie in diesem Beispiel basierend auf tatsächlichem Code gezeigt:

```cpp
#define CAT(a,b) a ## b
#define ECHO(...) __VA_ARGS__
// IMPL1 and IMPL2 are implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)

// MACRO chooses the expansion behavior based on the value passed to macro_switch
#define DO_THING(macro_switch, b) CAT(IMPL, macro_switch) ECHO(( "Hello", b))
DO_THING(1, "World");

// Traditional preprocessor:
// do_thing_one( "Hello", "World");
// Conformant preprocessor:
// IMPL1 ( "Hello","World");
```

Obwohl dieses Beispiel etwas erfunden ist, wurde es für den tatsächlichen Code gefunden. Um zu sehen, was passiert, können wir die Erweiterung unterbrechen, beginnend mit `DO_THING`:

1. `DO_THING(1, "World")` wird zu `CAT(IMPL, 1) ECHO(("Hello", "World"))` erweitert.
1. `CAT(IMPL, 1)` wird zu `IMPL ## 1` erweitert, die zu `IMPL1`
1. Die Token befinden sich nun in diesem Zustand: `IMPL1 ECHO(("Hello", "World"))`
1. Der Präprozessor findet den Funktions ähnlichen Makro Bezeichner `IMPL1`, es folgt jedoch kein `(`, sodass er nicht als Funktions ähnlicher Makro Aufruf angesehen wird. 
1. Es wechselt zu den folgenden Token und findet das Funktions ähnliche Makro `ECHO` aufgerufen wird: `ECHO(("Hello", "World"))`, das in erweitert wird `("Hello", "World")`
1. `IMPL1` für die Erweiterung nie als wieder betrachtet wird, ist das vollständige Ergebnis der Erweiterungen: `IMPL1("Hello", "World");`

Das Makro kann so geändert werden, dass es sich unter dem experimentellen Präprozessor und dem herkömmlichen Präprozessor verhält, indem es eine andere Dereferenzierungsschicht hinzufügt:

```cpp
#define CAT(a,b) a##b
#define ECHO(...) __VA_ARGS__
// IMPL1 and IMPL2 are macros implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)
#define CALL(macroName, args) macroName args
#define DO_THING_FIXED(a,b) CALL( CAT(IMPL, a), ECHO(( "Hello",b)))
DO_THING_FIXED(1, "World");

// macro expands to:
// do_thing_one( "Hello", "World");
```

## <a name="incomplete-features"></a>Unvollständige Features

Der experimentelle Präprozessor ist größtenteils fertig, auch wenn die Logik der Präprozessordirektive weiterhin auf das herkömmliche Verhalten zurückgreift. Im folgenden finden Sie eine Liste unvollständiger Features:

- Unterstützung für `_Pragma`
- C++ 20 Features
- Blockierungs Fehler verstärken: logische Operatoren in präprozessorkonstantenausdrücken sind im neuen Präprozessor nicht vollständig implementiert. Bei einigen `#if` Direktiven kann der neue Präprozessor auf den herkömmlichen Präprozessor zurückgreifen. Der Effekt ist nur sichtbar, wenn Makros, die mit dem herkömmlichen Präprozessor nicht kompatibel sind, erweitert werden. Dies kann beim Aufbau von Boost-präprozessorslots vorkommen.
