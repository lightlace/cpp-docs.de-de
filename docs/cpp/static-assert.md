---
title: static_assert
ms.date: 07/29/2019
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: 4ac79c23379dd1bf1c85521fdf0c28947d3b7ab9
ms.sourcegitcommit: 20a1356193fbe0ddd1002e798b952917eafc3439
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661582"
---
# <a name="staticassert"></a>static_assert

Überprüft eine Softwareassertion zur Kompilierzeit. Wenn der angegebene Konstante Ausdruck false ist, zeigt der Compiler die angegebene Meldung an, sofern eine vorhanden ist, und bei der Kompilierung tritt ein Fehler auf C2338; Andernfalls hat die Deklaration keine Auswirkungen.

## <a name="syntax"></a>Syntax

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // C++17 (Visual Studio 2017 and later)
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*constant-expression*|Ein ganzzahliger konstanter Ausdruck, der in einen booleschen Wert konvertiert werden kann.<br /><br /> Wenn der ausgewertete Ausdruck NULL (false) ist, wird der *String-* literalparameter angezeigt, und bei der Kompilierung tritt ein Fehler auf. Wenn der Ausdruck ungleich 0 (true) ist, hat die **static_assert** -Deklaration keine Auswirkungen.|
|*string-literal*|Eine Meldung, die angezeigt wird, wenn der *Constant-Expression-* Parameter 0 (null) ist. Die Meldung ist eine Zeichenfolge im [Basis Zeichensatz](../c-language/ascii-character-set.md) des Compilers. Das heißt, es handelt sich nicht um [Multibytezeichen-oder breit Zeichen](../c-language/multibyte-and-wide-characters.md).|

## <a name="remarks"></a>Hinweise

Der *Constant-Expression-* Parameter einer **static_assert** -Deklaration stellt eine *Software*Assertion dar. Eine Softwareassertion gibt eine Bedingung an, die an einer bestimmten Stelle im Programm "true" sein muss. Wenn die Bedingung true ist, hat die **static_assert** -Deklaration keine Auswirkungen. Wenn die Bedingung "false" lautet, schlägt die-Übersetzung fehl, der Compiler zeigt die Meldung im *String-* literalparameter an, und die Kompilierung schlägt mit einem Fehler fehl. In Visual Studio 2017 und höher ist der String-literalparameter optional.

Die **static_assert** -Deklaration testet eine Software-Assertion zur Kompilierzeit. Im Gegensatz dazu testen die [Funktionen ASSERT-Makro und _ASSERT und _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) eine Software-Assertion zur Laufzeit und verursachen einen Lauf Zeitaufwand im Bereich oder in der Zeit. Die **static_assert** -Deklaration ist besonders nützlich für das Debuggen von Vorlagen, da Vorlagen Argumente im *Constant-Expression-* Parameter enthalten sein können.

Der Compiler überprüft die **static_assert** -Deklaration auf Syntax Fehler, wenn die Deklaration gefunden wird. Der Compiler wertet den *Constant-Expression-* Parameter sofort aus, wenn er nicht von einem Vorlagen Parameter abhängt. Andernfalls wertet der Compiler den *Constant-Expression-* Parameter aus, wenn die Vorlage instanziiert wird. Daher gibt der Compiler möglicherweise eine Diagnosemeldung aus: einmal, wenn die Deklaration gefunden wird, und noch einmal, wenn die Vorlage instanziiert wird.

Sie können das **static_assert** -Schlüsselwort im Namespace, in der Klasse oder im Block Bereich verwenden. (Das **static_assert** -Schlüsselwort ist technisch gesehen eine Deklaration, obwohl es keinen neuen Namen in Ihr Programm einführt, da es im Namespace Bereich verwendet werden kann.)

## <a name="description"></a>Beschreibung

Im folgenden Beispiel weist die **static_assert** -Deklaration den Namespace Bereich auf. Da der Compiler die Größe des Typs `void *` kennt, wird der Ausdruck sofort ausgewertet.

## <a name="example"></a>Beispiel

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description"></a>Beschreibung

Im folgenden Beispiel verfügt die **static_assert** -Deklaration über einen Klassen Bereich. **Static_assert** überprüft, ob ein Vorlagen Parameter ein *Plain Old Data* (Pod)-Typ ist. Der Compiler überprüft die **static_assert** -Deklaration, wenn er deklariert wird, wertet den *Constant-Expression-* Parameter jedoch `basic_string` erst aus, wenn die Klassen Vorlage `main()`in instanziiert wird.

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

Im folgenden Beispiel verfügt die **static_assert** -Deklaration über einen Block Bereich. **Static_assert** überprüft, ob die Größe der VMPage-Struktur gleich der Größe des virtuellen Arbeitsspeichers des Systems ist.

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