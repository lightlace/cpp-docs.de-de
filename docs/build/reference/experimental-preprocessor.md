---
title: '/experimental: Präprozessor (präprozessorübereinstimmungs Modus aktivieren)'
description: 'Verwenden Sie die/Experimental: präprocessor-Compileroption, um die experimentelle Compilerunterstützung für einen standardkonformen Präprozessor zu aktivieren'
ms.date: 09/03/2019
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 3055cfa2a32d1d668dbe0c51b5542415b5bb0af4
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70294437"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>/experimental: Präprozessor (präprozessorübereinstimmungs Modus aktivieren)

Diese Option ermöglicht einen experimentellen, tokenbasierten Präprozessor, der den c++ 11-Standards entspricht, einschließlich C99-präprozessorfunktionen.

## <a name="syntax"></a>Syntax

> **/experimental: Präprozessor** [ **-** ]

## <a name="remarks"></a>Hinweise

Verwenden Sie die **/experimental: präprocessor** -Compileroption, um den experimentellen, konformen Präprozessor zu aktivieren. Mit **/experimental: Preprocessor-** Option können Sie den herkömmlichen Präprozessor explizit angeben.

Die Option **/experimental: präprocessor** ist ab Visual Studio 2017 Version 15,8 verfügbar.

Sie können erkennen, welcher Präprozessor zum Zeitpunkt der Kompilierung verwendet wird. Überprüfen Sie den Wert des vordefinierten Makros [ \_MSVC\_Traditional](../../preprocessor/predefined-macros.md) , um zu ermitteln, ob der herkömmliche Präprozessor bereits verwendet wird. Dieses Makro wird von Versionen des Compilers, die es unterstützen, bedingungslos festgelegt, unabhängig davon, welcher Präprozessor aufgerufen wird. Der Wert für den herkömmlichen Präprozessor ist 1. Der Wert 0 für den konformen experimentellen Präprozessor:

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

### <a name="behavior-changes-in-the-experimental-preprocessor"></a>Verhaltensänderungen im experimentellen Präprozessor

Im folgenden finden Sie einige der gängigeren wichtigen Änderungen, die beim Aktivieren des präprozessorübereinstimmungs Modus gefunden werden:

#### <a name="macro-comments"></a>Makro Kommentare

Der herkömmliche Präprozessor verwendet Zeichen Puffer anstelle von Präprozessortoken. Dies ermöglicht ungewöhnliche Verhaltensweisen, wie z. b. diesen präprozessorkommentartrick, der nicht im konformen Präprozessor funktioniert:

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
// To make standards compliant, wrap the following line with the appropriate #if/#endif
DISAPPEARING_TYPE myVal;
```

#### <a name="string-prefixes-lval"></a>Zeichen folgen Präfixe (L # Val)

Der herkömmliche Präprozessor kombiniert fälschlicherweise ein Zeichen folgen Präfix mit dem Ergebnis des Zeichen folgen [Operators (#)](../../preprocessor/stringizing-operator-hash.md):

```cpp
#define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

Das `L` Präfix ist hier nicht erforderlich, da die angrenzenden Zeichenfolgenliterale nach der Makro Erweiterung immer kombiniert werden. Die abwärts kompatible Korrektur besteht darin, die Definition in zu ändern:

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

Dieses Problem ist auch in den hilfsproblem zu finden, die das Argument für ein breites Zeichenfolgenliteralzeichen ' stringisieren

```cpp
// The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str

// Potential fixes:
// Use string concatenation of L"" and #str to add prefix
// This works because adjacent string literals are combined after macro expansion
#define STRING1(str) L""#str

// Add the prefix after #str is stringized with additional macro expansion
#define WIDE(str) L##str
#define STRING2(str) WIDE(#str)

// Use concatenation operator ## to combine the tokens.
// The order of operations for ## and # is unspecified, although all compilers
// checked perform the # operator before ## in this case.
#define STRING3(str) L## #str
```

#### <a name="warning-on-invalid"></a>Warnung bei ungültigem ##

Wenn der [tokeneinfügenden Operator (# #)](../../preprocessor/token-pasting-operator-hash-hash.md) nicht zu einem einzelnen, gültigen Vorverarbeitungs Token führt, ist das Verhalten nicht definiert. Der herkömmliche präprozessorvorgang kann die Token nicht kombinieren. Der neue Präprozessor entspricht dem Verhalten der meisten anderen Compiler und gibt eine Diagnose aus.

```cpp
// The ## is unnecessary and doesn't result in a single preprocessing token.
#define ADD_STD(x) std::##x

// Declare a std::string
ADD_STD(string) s;
```

#### <a name="comma-elision-in-variadic-macros"></a>Komma-elisions in Variadic-Makros

Betrachten Sie das folgende Beispiel:

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // The following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor replaces the following macro with:
    // func(1, );
    // which results in a syntax error.
    FUNC(1, );
}
```

Alle Haupt Compiler verfügen über eine PräprozessorErweiterung, die zur Behebung dieses Problems beiträgt. Der herkömmliche MSVC-Präprozessor entfernt vor leeren `__VA_ARGS__` Ersetzungen immer Kommas. Der aktualisierte Präprozessor folgt genauer an das Verhalten anderer beliebter plattformübergreifender Compiler. Damit das Komma entfernt wird, muss das Variadic-Argument fehlt, nicht nur leer sein, und es muss mit einem `##` Operator gekennzeichnet werden:

```cpp
#define FUNC2(a, ...) func(a , ## __VA_ARGS__)
int main()
{
    // The variadic argument is missing in the macro being evoked
    // The comma is removed and replaced with:
    // func(1)
    FUNC2(1);

    // The variadic argument is empty, but not missing. (Notice the
    // comma in the argument list.) The comma isn't removed
    // when the macro is replaced:
    // func(1, )
    FUNC2(1, );
}
```

Im bevorstehenden C + + 2A-Standard wurde dieses Problem durch Hinzufügen `__VA_OPT__`von behoben, das noch nicht implementiert wurde.

#### <a name="macro-arguments-are-unpacked"></a>Makro Argumente sind "entpackt"

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

Beim Erweitern `A()`leitet der herkömmliche Präprozessor alle in `__VA_ARGS__` paketierten Argumente an das erste Argument von `TWO_STRINGS`weiter. Das Variadic-Argument `TWO_STRINGS` von ist leer, was bewirkt, dass `#first` das Ergebnis `"1, 2"` von nicht nur `"1"`ist. Sie Fragen sich vielleicht, was mit dem Ergebnis `#__VA_ARGS__` von in der herkömmlichen PräprozessorErweiterung passiert ist. Wenn der Variadic-Parameter leer ist, sollte ein leeres Zeichenfolgenliteralzeichen "" angezeigt werden. Aufgrund eines separaten Problems wurde das leere zeichenfolgenliteraltoken nicht generiert.

#### <a name="rescanning-replacement-list-for-macros"></a>Die Ersetzungs Liste für Makros wird neu berechnet.

Nachdem ein Makro ersetzt wurde, werden die sich ergebenden Token neu berechnet, um weitere Makro Bezeichner zu ersetzen. Der vom herkömmlichen Präprozessor verwendete neu einlesen-Algorithmus ist nicht konform, wie in diesem Beispiel basierend auf tatsächlichem Code gezeigt:

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

Um zu sehen, was in diesem Beispiel passiert, unterbrechen wir die Erweiterung ab `DO_THING`:

`DO_THING(1, "World")` ->
`CAT(IMPL, 1) ECHO(("Hello", "World"))`

Zweitens ist Cat erweitert:

`CAT(IMPL, 1)` -> `IMPL ## 1` -> `IMPL1`

Dadurch werden die Token in diesen Zustand versetzt:

`IMPL1 ECHO(("Hello", "World"))`

Der Präprozessor findet den Funktions ähnlichen Makro Bezeichner `IMPL1`, es folgt jedoch kein "(", sodass er nicht als Funktions ähnlicher Makro Aufruf angesehen wird. Es wechselt zu den folgenden Token und findet das Funktions ähnliche Makro `ECHO` , das aufgerufen wird:

`ECHO(("Hello", "World"))` -> `("Hello", "World")`

`IMPL1`wird nie für die Erweiterung wieder in Erwägung gezogen, daher lautet das vollständige Ergebnis der Erweiterungen wie folgt:

`IMPL1("Hello", "World");`

Das-Makro kann so geändert werden, dass es sich auf die gleiche Weise unter dem experimentellen Präprozessor und dem herkömmlichen Präprozessor verhält. Die Lösung besteht darin, eine weitere Dereferenzierungsschicht hinzuzufügen:

```cpp
#define CAT(a,b) a##b
#define ECHO(...) __VA_ARGS__

// IMPL1 and IMPL2 are macros implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)

#define CALL(macroName, args) macroName args
#define DO_THING_FIXED(a,b) CALL( CAT(IMPL, a), ECHO(( "Hello",b)))

DO_THING_FIXED(1, "World");
// macro expanded to:
// do_thing_one( "Hello", "World");
```

### <a name="conformance-mode-conformance"></a>Konformität des Konformitäts Modus

Der experimentelle Präprozessor ist noch nicht fertig, und die Logik der Präprozessordirektive greift weiterhin auf das herkömmliche Verhalten zurück. Im folgenden finden Sie eine Liste unvollständiger Features:

- Unterstützung für`_Pragma`
- C++ 20 Features
- Zusätzliche Diagnose Verbesserungen
- Schaltet ein, um die Ausgabe unter/E und/P zu steuern.
- Blockierungs Fehler verstärken: Logische Operatoren in präprozessorkonstantenausdrücken sind im neuen Präprozessor nicht vollständig implementiert. Bei einigen `#if` Direktiven kann der neue Präprozessor auf den herkömmlichen Präprozessor zurückgreifen. Der Effekt ist nur sichtbar, wenn Makros, die mit dem herkömmlichen Präprozessor nicht kompatibel sind, erweitert werden. Dies kann beim Aufbau von Boost-präprozessorslots vorkommen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++**  > **Befehlszeile**.

1. Ändern Sie die Eigenschaft **zusätzliche Optionen** so, dass Sie **/experimental: Preprocessor** einschließt, und wählen Sie dann **OK**aus.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](zc-conformance.md)
