---
title: static_assert
ms.date: 11/04/2016
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: d5ef1ba45001a2b1a3ee1f2da46f66224857b070
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668974"
---
# <a name="staticassert"></a>static_assert

Überprüft eine Softwareassertion zur Kompilierzeit. Wenn der angegebene Konstante Ausdruck "false" ist, zeigt der Compiler die angegebene Meldung, aus, wenn eine bereitgestellt wird und die Kompilierung schlägt mit Fehler C2338 fehl; Andernfalls hat die Deklaration keine Auswirkungen.

## <a name="syntax"></a>Syntax

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // Visual Studio 2017 and later
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*constant-expression*|Ein ganzzahliger konstanter Ausdruck, der in einen booleschen Wert konvertiert werden kann.<br /><br /> Wenn der ausgewertete Ausdruck 0 (null) ist (false), die *Zeichenfolgenliteral* Parameter angezeigt wird, und die Kompilierung schlägt fehl. Wenn der Ausdruck ungleich Null (True), ist die **"static_assert"** Deklaration hat keine Auswirkungen.|
|*string-literal*|Eine Nachricht, die angezeigt wird, wenn die *Konstantenausdruck* -Parameter ist 0 (null). Die Meldung ist eine Zeichenfolge von Zeichen in der [Basis-Zeichensatz](../c-language/ascii-character-set.md) von der Compilers, d. h., nicht [Multibyte-oder Breitzeichen](../c-language/multibyte-and-wide-characters.md).|

## <a name="remarks"></a>Hinweise

Die *Konstantenausdruck* Parameter eine **"static_assert"** Deklaration stellt einen *Softwareassertion*. Eine Softwareassertion gibt eine Bedingung an, die an einer bestimmten Stelle im Programm "true" sein muss. Wenn die Bedingung "true" ist die **"static_assert"** Deklaration hat keine Auswirkungen. Wenn die Bedingung false ist, schlägt die Assertion fehl, zeigt der Compiler die Nachricht in *Zeichenfolgenliteral* -Parameter und der Kompilierung tritt ein Fehler. Der Zeichenfolgenliteral-Parameter ist optional, in Visual Studio 2017 und höher.

Die **"static_assert"** -Deklaration testet eine Softwareassertion zur Kompilierzeit. Im Gegensatz dazu die [assert-Makro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) Makro testet eine Softwareassertion zur Laufzeit und fallen Kosten an, zur Laufzeit auf Speicherplatz und Zeit. Die **"static_assert"** -Deklaration ist besonders nützlich zum Debuggen von Vorlagen, da Vorlagenargumente in aufgenommen werden können die *Konstantenausdruck* Parameter.

Der Compiler überprüft die **"static_assert"** -Deklaration auf Syntaxfehler, wenn die Deklaration gefunden wird. Der Compiler wertet die *Konstantenausdruck* Parameter sofort, wenn es nicht von einem Vorlagenparameter abhängt. Der Compiler andernfalls wertet der *Konstantenausdruck* Parameter an, wenn die Vorlage instanziiert wird. Daher gibt der Compiler möglicherweise eine Diagnosemeldung aus: einmal, wenn die Deklaration gefunden wird, und noch einmal, wenn die Vorlage instanziiert wird.

Sie können die **"static_assert"** Schlüsselwort an den Namespace, Klassen- oder Blockbereich. (Die **"static_assert"** -Schlüsselwort ist technisch gesehen eine Deklaration, obwohl es keine neuen Namen in das Programm einführt, da es im Namespacebereich verwendet werden kann.)

## <a name="description"></a>Beschreibung

Im folgenden Beispiel die **"static_assert"** -Deklaration über einen Namespace-Gültigkeitsbereich. Da der Compiler die Größe des Typs `void *` kennt, wird der Ausdruck sofort ausgewertet.

## <a name="example"></a>Beispiel

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description"></a>Beschreibung

Im folgenden Beispiel die **"static_assert"** Deklaration über einen Klassenbereich. Die **"static_assert"** überprüft, ob ein Vorlagenparameter ist eine *plain old Data* (POD)-Typ. Der Compiler überprüft die **"static_assert"** -Deklaration wird deklariert, jedoch wird nicht ausgewertet den *Konstantenausdruck* Parameter bis der `basic_string` -Klassenvorlage in instanziiert`main()`.

## <a name="example"></a>Beispiel

```cpp
#include <type_traits>
#include <iosfwd>
namespace std {
template <class CharT, class Traits = std::char_traits<CharT> >
class basic_string {
    static_assert(std::is_pod<CharT>::value,
                  "Template argument CharT must be a POD type in class template basic_string");
    // ...
    };
}

struct NonPOD {
    NonPOD(const NonPOD &) {}
    virtual ~NonPOD() {}
};

int main()
{
    std::basic_string<char> bs;
}
```

## <a name="description"></a>Beschreibung

Im folgenden Beispiel die **"static_assert"** Deklaration einen Blockbereich aufweist. Die **"static_assert"** stellt sicher, dass die Größe der VMPage-Struktur der Seitengröße virtuellen Arbeitsspeicher des Systems entspricht.

## <a name="example"></a>Beispiel

```cpp
#include <sys/param.h> // defines PAGESIZE
class VMMClient {
public:
    struct VMPage { // ...
           };
    int check_pagesize() {
    static_assert(sizeof(VMPage) == PAGESIZE,
        "Struct VMPage must be the same size as a system virtual memory page.");
    // ...
    }
// ...
};
```

## <a name="see-also"></a>Siehe auch

[Assertion und benutzerdefinierte Meldungen (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)<br/>
[#error-Direktive (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[Vorlagen](../cpp/templates-cpp.md)<br/>
[ASCII-Zeichensatz](../c-language/ascii-character-set.md)<br/>
[Deklarationen und Definitionen](declarations-and-definitions-cpp.md)