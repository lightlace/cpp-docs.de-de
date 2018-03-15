---
title: '-Zc: NoexceptTypes (C ++ 17 Regeln Noexcept) | Microsoft Docs'
ms.date: 11/14/2017
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc:noexceptTypes
dev_langs:
- C++
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af455b9a781295f3e6f446b7dc5c3d253fe2f4c5
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (C ++ 17 Regeln Noexcept)

Macht die C ++ 17-standard `throw()` als Alias für `noexcept`, entfernt `throw(<type list>)` und `throw(...)`, und Sie können bestimmte Typen enthalten `noexcept`. Dies kann eine Anzahl von Kompatibilitätsproblemen Quelle im Code verursachen, die auf C ++ 14 oder niedriger entspricht. Die **/Zc:noexceptTypes** Option kann Konformität mit der C ++ 17-standard angeben oder die C ++ 14 und frühere Verhalten zulassen, wenn Code im C ++ 17-Modus kompiliert wird.

## <a name="syntax"></a>Syntax

> **/Zc:noexceptTypes**[-]

## <a name="remarks"></a>Hinweise

Wenn die **/Zc:noexceptTypes** angegeben wird, der Compiler die C ++ 17-standard entspricht und behandelt [throw()](../../cpp/exception-specifications-throw-cpp.md) als Alias für [Noexcept](../../cpp/noexcept-cpp.md), entfernt `throw(<type list>)`und `throw(...)`, und Sie können bestimmte Typen enthalten `noexcept`. Die **/Zc:noexceptTypes** Option ist nur verfügbar, wenn [/std:c ++ 17](std-specify-language-standard-version.md) oder [/std:latest](std-specify-language-standard-version.md) aktiviert ist. **/Zc:noexceptTypes** ist standardmäßig aktiviert, die ISO C ++ 17-standard entsprechen. Die [/ liberalen-](permissive-standards-conformance.md) Option wirkt sich nicht **/Zc:noexceptTypes**. Diese Option deaktivieren, indem Sie die Angabe **/Zc:noexceptTypes-** , um den C ++ 14 Verhalten wiederherzustellen `noexcept` Wenn **/std::C ++ 17** oder **/std::latest** angegeben ist.

In Visual Studio 2017 Version 15.5 ab, der C++-Compiler diagnostiziert weitere nicht übereinstimmende Ausnahmespezifikationen in Deklarationen in C ++ 17-Modus oder wenn die [/ liberalen-](permissive-standards-conformance.md) angegeben wird.

In diesem Beispiel wird gezeigt, wie Deklarationen mit einem ausnahmebezeichner verhält, wenn die **/Zc:noexceptTypes** Option festgelegt oder deaktiviert ist. Das Verhalten bei der Einstellung, kompilieren Sie mit `cl /EHsc /W4 noexceptTypes.cpp`. Um das Verhalten bei deaktivierter anzuzeigen, kompilieren Sie mit `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`.

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

Beim Kompilieren mit der Standardeinstellung **/Zc:noexceptTypes**, im Beispiel wird die aufgeführten Warnungen generiert. Zum Aktualisieren des Codes verwenden Sie stattdessen Folgendes:

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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc:noexceptTypes** oder **/Zc:noexceptTypes-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)  
[noexcept](../../cpp/noexcept-cpp.md)  
[Ausnahmespezifikationen (throw)](../../cpp/exception-specifications-throw-cpp.md)  
