---
title: /Zc:noexceptTypes (noexcept-Regeln für C++17)
ms.date: 11/14/2017
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: 35bea7c2c629c615c60a6136f289b6b11926c054
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624869"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (noexcept-Regeln für C++17)

Der c++ 17-Standard stellt `throw()` einen Alias für `noexcept`, entfernt `throw(<type list>)` und `throw(...)`und ermöglicht es, dass bestimmte Typen `noexcept`einschließen. Diese Änderung kann eine Reihe von Problemen mit der Quell Kompatibilität in Code verursachen, der c++ 14 oder früher entspricht. Die Option **/Zc: noexcepttypes** gibt eine Übereinstimmung mit dem c++ 17-Standard an. **/Zc: noexcepttypes-** ermöglicht das c++ 14-und frühere Verhalten, wenn Code im c++ 17-Modus kompiliert wird.

## <a name="syntax"></a>Syntax

> **/Zc: noexcepttypes**[-]

## <a name="remarks"></a>Hinweise

Wenn die **/Zc: noexcepttypes** -Option angegeben wird, entspricht der Compiler dem c++ 17-Standard und behandelt [throw ()](../../cpp/exception-specifications-throw-cpp.md) als Alias für [noaußer](../../cpp/noexcept-cpp.md), entfernt `throw(<type list>)` und `throw(...)`und ermöglicht, dass bestimmte Typen `noexcept`einschließen. Die **/Zc: noexcepttypes** -Option ist nur verfügbar, wenn [/Std: c++ 17](std-specify-language-standard-version.md) oder [/Std: Latest](std-specify-language-standard-version.md) aktiviert ist. **/Zc: noexcepttypes** ist standardmäßig aktiviert, um dem ISO c++ 17-Standard zu entsprechen. Die [/permissive-](permissive-standards-conformance.md) -Option hat keine Auswirkung auf **/Zc: noexcepttypes**. Deaktivieren Sie diese Option, indem Sie **/Zc: noexcepttypes** angeben, um zum c++ 14-Verhalten von `noexcept` zurückzukehren, wenn **/Std: c++ 17** oder **/Std: Latest** angegeben wird.

Ab Visual Studio 2017 Version 15,5 diagnostiziert der C++ Compiler eher nicht übereinstimmende Ausnahme Spezifikationen in Deklarationen im c++ 17-Modus oder wenn Sie die [/permissive-](permissive-standards-conformance.md) -Option angeben.

Dieses Beispiel zeigt, wie sich Deklarationen mit einem ausnahmespezifizierer Verhalten, wenn die Option **/Zc: noexcepttypes** festgelegt oder deaktiviert ist. Um das Verhalten beim Festlegen anzuzeigen, kompilieren Sie mit `cl /EHsc /W4 noexceptTypes.cpp`. Kompilieren Sie mit `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`, um das Verhalten bei der Deaktivierung anzuzeigen.

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

Bei der Kompilierung mit der Standardeinstellung **/Zc: noexcepttypes**generiert das Beispiel die aufgelisteten Warnungen. Um Ihren Code zu aktualisieren, verwenden Sie stattdessen Folgendes:

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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++**  > **Befehlszeile**.

1. Ändern Sie die Eigenschaft **zusätzliche Optionen** so, dass Sie **/Zc: noexcepttypes** oder **/Zc: noexcepttypes** enthält, und wählen Sie dann **OK**aus.

## <a name="see-also"></a>Siehe auch

[/Zc (Konformität)](zc-conformance.md)\
[noaußer](../../cpp/noexcept-cpp.md)\
[Ausnahme Spezifikationen (Throw)](../../cpp/exception-specifications-throw-cpp.md)
