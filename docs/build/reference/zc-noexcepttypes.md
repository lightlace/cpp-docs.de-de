---
title: /Zc:noexceptTypes (C++17 noexcept rules)
ms.date: 11/14/2017
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: 28e06f54049d36262134b6be7eadb0e6e5349a45
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812108"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (C++17 noexcept rules)

Stellt den C ++ 17-standard `throw()` als Alias für `noexcept`, entfernt `throw(<type list>)` und `throw(...)`, und Sie können bestimmte Typen umfassen `noexcept`. Dies kann eine Anzahl von quellkompatibilitätsproblemen im Code verursachen, die mit C ++ 14 oder früher konform. Die **/Zc: noexcepttypes** Option kann oder Angeben der Übereinstimmung mit den C ++ 17-standard können Sie die C ++ 14 und frühere Verhalten, wenn Code im C ++ 17-Modus kompiliert wird.

## <a name="syntax"></a>Syntax

> **/Zc:noexceptTypes**[-]

## <a name="remarks"></a>Hinweise

Wenn die **/Zc: noexcepttypes** angegeben wurde, wird der Compiler den C ++ 17-standard entspricht, und behandelt [throw()](../../cpp/exception-specifications-throw-cpp.md) als Alias für ["noexcept"](../../cpp/noexcept-cpp.md), entfernt `throw(<type list>)`und `throw(...)`, und Sie können bestimmte Typen umfassen `noexcept`. Die **/Zc: noexcepttypes** Option ist nur verfügbar, wenn [/Std: c ++ 17](std-specify-language-standard-version.md) oder [/std:latest](std-specify-language-standard-version.md) aktiviert ist. **/ Zc: noexcepttypes** ist standardmäßig aktiviert, der ISO C ++ 17-standard entsprechen. Die [/ PERMISSIVE--](permissive-standards-conformance.md) Option hat keine Auswirkungen auf **/Zc: noexcepttypes**. Diese Option deaktivieren, indem Sie angeben **/Zc:noexceptTypes-** , in das C ++ 14 Verhalten zurückzukehren `noexcept` beim **/std::C ++ 17** oder **/std::latest** angegeben ist.

Visual Studio 2017 Version 15.5 ab, der C++-Compiler diagnostiziert weitere nicht übereinstimmender Ausnahmespezifikationen in Deklarationen im C ++ 17-Modus oder den [/ PERMISSIVE--](permissive-standards-conformance.md) angegeben wird.

Dieses Beispiel zeigt, wie Deklarationen mit einem ausnahmebezeichner verhält, wenn die **/Zc: noexcepttypes** Option deaktiviert oder festgelegt ist. Das Verhalten bei Festlegung, kompilieren Sie mit `cl /EHsc /W4 noexceptTypes.cpp`. Um das Verhalten, wenn deaktiviert anzuzeigen, kompilieren Sie mit `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`.

```cpp
// noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp

void f() throw();    // equivalent to void f() noexcept;
void f() { }         // warning C5043
void g() throw(...); // warning C5040

struct A
{
    virtual void f() throw();
};

struct B : A
{
    virtual void f() { } // error C2694
};
```

Beim Kompilieren mit der Standardeinstellung **/Zc: noexcepttypes**, im Beispiel wird die aufgeführten Warnungen generiert. Um den Code aktualisieren, verwenden Sie stattdessen Folgendes:

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A
{
    virtual void f() noexcept;
};

struct B : A
{
    virtual void f() noexcept { }
};
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc: noexcepttypes** oder **/Zc:noexceptTypes-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[Ausnahmespezifikationen (throw)](../../cpp/exception-specifications-throw-cpp.md)
