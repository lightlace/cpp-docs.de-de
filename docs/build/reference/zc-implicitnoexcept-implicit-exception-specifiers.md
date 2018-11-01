---
title: /Zc:implicitNoexcept (implizite Ausnahmespezifizierer)
ms.date: 03/06/2018
f1_keywords:
- /Zc:implicitNoexcept
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
ms.openlocfilehash: 0ca03cc2a3afa0d5665f217ccb0d41eb1e41d3be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480929"
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/Zc:implicitNoexcept (implizite Ausnahmespezifizierer)

Wenn die **/Zc: implicitnoexcept** angegeben wird, es fügt der Compiler einen impliziten ["noexcept"](../../cpp/noexcept-cpp.md) ausnahmebezeichner compilerdefinierten spezielle Memberfunktionen und benutzerdefinierten Destruktoren und deallokatoren. In der Standardeinstellung **/Zc: implicitnoexcept** ist aktiviert, um dem ISO C ++ 11-standard entsprechen. Durch Deaktivieren dieser Option wird für das implizite `noexcept`-Element für benutzerdefinierte Destruktoren und Deallokatoren und die speziellen vom Compiler definierten Memberfunktionen deaktiviert.

## <a name="syntax"></a>Syntax

> **/Zc:implicitNoexcept**[**-**]

## <a name="remarks"></a>Hinweise

**/ Zc: implicitnoexcept** weist den Compiler Abschnitt 15.4 des ISO C ++ 11-standard befolgen. Implizit hinzugefügt eine `noexcept` -ausnahmebezeichner hinzu jeder implizit deklarierten oder explizit auf den Standardwert festgelegte spezielle Memberfunktion – der Standardkonstruktor, kopieren, Konstruktor, bewegungskonstruktor, Destruktor, Kopierzuweisungsoperator oder verschieben Sie Zuweisung Operator – und jeder benutzerdefinierten Destruktor- oder deallokatorfunktion-Funktion. Ein benutzerdefinierter Deallokator verfügt über einen impliziten `noexcept(true)`-Ausnahmebezeichner. Für benutzerdefinierte Destruktoren ist `noexcept(true)` der implizite Ausnahmebezeichner, es sei denn eine enthaltene Elementklasse oder Basisklasse weist einen Destruktor auf, der nicht `noexcept(true)` ist. Für vom Compiler generierte spezielle Memberfunktionen ist `noexcept(false)` der implizite Ausnahmebezeichner, wenn eine von dieser Funktion aufgerufene Funktion `noexcept(false)` ist. Andernfalls ist `noexcept(true)` der implizite Ausnahmebezeichner.

Für Funktionen, die mit expliziten `noexcept`- oder `throw`-Bezeichnern oder einem `__declspec(nothrow)`-Attribut deklariert wurden, generiert der Compiler keinen impliziten Ausnahmebezeichner.

In der Standardeinstellung **/Zc: implicitnoexcept** aktiviert ist. Die [/ PERMISSIVE--](permissive-standards-conformance.md) Option hat keine Auswirkungen auf **/Zc: implicitnoexcept**.

Wenn die Option, durch Angabe deaktiviert ist **/Zc:implicitNoexcept-**, werden keine impliziten ausnahmebezeichner vom Compiler generiert. Dieses Verhalten ist mit dem in Visual Studio 2013 identisch, wo Destruktoren und Deallokatoren ohne Ausnahmebezeichner über `throw`-Anweisungen verfügen können. In der Standardeinstellung und wann **/Zc: implicitnoexcept** angegeben wird, wenn eine `throw` -Anweisung zur Laufzeit in eine Funktion mit einem impliziten gefunden `noexcept(true)` Bezeichner verursacht einen unmittelbaren Aufruf `std::terminate`, und normales entladungsverhalten für Ausnahmehandler ist nicht garantiert. Um diese Situation zu identifizieren, generiert der Compiler [Compilerwarnung (Stufe 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md). Wenn die `throw` ist beabsichtigt, sollten Sie ändern die Funktionsdeklaration, dass eine explizite `noexcept(false)` Spezifizierer anstelle von **/Zc:implicitNoexcept-**.

Dieses Beispiel zeigt ein benutzerdefinierten Destruktor, die keine expliziten ausnahmebezeichner beim Verhalten der **/Zc: implicitnoexcept** Option deaktiviert oder festgelegt ist. Das Verhalten bei Festlegung, kompilieren Sie mit `cl /EHsc /W4 implicitNoexcept.cpp`. Um das Verhalten, wenn deaktiviert anzuzeigen, kompilieren Sie mit `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`.

```cpp
// implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp

#include <iostream>
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS
#include <exception>    // for std::set_terminate

void my_terminate()
{
    std::cout << "Unexpected throw caused std::terminate" << std::endl;
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;
    std::exit(EXIT_FAILURE);
}

struct A {
    // Explicit noexcept overrides implicit exception specification
    ~A() noexcept(false) {
        throw 1;
    }
};

struct B : public A {
    // Compiler-generated ~B() definition inherits noexcept(false)
    ~B() = default;
};

struct C {
    // By default, the compiler generates an implicit noexcept(true)
    // specifier for this user-defined destructor. To enable it to
    // throw an exception, use an explicit noexcept(false) specifier,
    // or compile by using /Zc:implicitNoexcept-
    ~C() {
        throw 1; // C4297, calls std::terminate() at run time
    }
};

struct D : public C {
    // This destructor gets the implicit specifier of its base.
    ~D() = default;
};

int main()
{
    std::set_terminate(my_terminate);

    try
    {
        {
            B b;
        }
    }
    catch (...)
    {
        // exception should reach here in all cases
        std::cout << "~B Exception caught" << std::endl;
    }
    try
    {
        {
            D d;
        }
    }
    catch (...)
    {
        // exception should not reach here if /Zc:implicitNoexcept
        std::cout << "~D Exception caught" << std::endl;
    }
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;
    return EXIT_SUCCESS;
}
```

Beim Kompilieren mit der Standardeinstellung **/Zc: implicitnoexcept**, im Beispiel wird diese Ausgabe generiert:

```Output
~B Exception caught
Unexpected throw caused std::terminate
Exit returning EXIT_FAILURE
```

Beim Kompilieren mit der Einstellung **/Zc:implicitNoexcept-**, im Beispiel wird diese Ausgabe generiert:

```Output
~B Exception caught
~D Exception caught
Exit returning EXIT_SUCCESS
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc: implicitnoexcept** oder **/Zc:implicitNoexcept-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[Ausnahmespezifikationen (throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[terminate](../../standard-library/exception-functions.md#terminate)<br/>
