---
title: extern (C++)
ms.date: 04/12/2018
f1_keywords:
- extern
- extern_CPP
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
ms.openlocfilehash: 4a3a4e158794e06f28c638e87e014ddc3fb99837
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183738"
---
# <a name="extern-c"></a>extern (C++)

Die **"extern"** -Schlüsselwort angewendet wird, auf eine globale Variable, Funktion oder Vorlage Deklaration festlegen, dass der Name des, daran hat *externe Verknüpfung*. Weitere Informationen zu Verknüpfungen und warum wird die Verwendung der globalen Variablen nicht empfohlen, finden Sie unter [Programm und Verknüpfung](program-and-linkage-cpp.md).

Die **"extern"** Schlüsselwort hat vier Bedeutungen, abhängig vom Kontext:

1. in einer globalen Variablen nicht-Const-Deklaration **"extern"** gibt an, dass die Variable oder Funktion in einer anderen Übersetzungseinheit definiert ist. Die **"extern"** angewendet werden muss, in allen Dateien mit Ausnahme der, in dem die Variable definiert ist.
1. in einer Variablendeklaration const gibt es, dass die Variable eine externe Bindung verfügt. Die **"extern"** muss auf allen Deklarationen in der alle Dateien angewendet werden. (Globale Konstante Variablen eine interne Bindung haben in der Standardeinstellung.)
1. **Extern "C"** gibt an, dass die Funktion an anderer Stelle definiert ist und die Programmiersprache C-Aufrufkonvention verwendet. Extern "C"-Modifizierer kann auch auf mehrere Deklarationen in einen Block angewendet werden.
1. in einer Vorlagendeklaration gibt es an, dass die Vorlage bereits an anderer Stelle instanziiert wurde. Dies ist eine Optimierung, die dem Compiler mitteilt, an der aktuellen Position einen neuen zu erstellen, anstatt die anderen Instanziierung erneut verwendet werden kann. Weitere Informationen zu dieser Verwendung von **"extern"**, finden Sie unter [Vorlagen](templates-cpp.md).

## <a name="extern-linkage-for-non-const-globals"></a>externe Verknüpfung für nicht-Const-globals

Wenn der Linker sieht **"extern"** vor der Deklaration einer globalen Variablen, sucht die Definition in einer anderen Übersetzungseinheit. Deklarationen von nicht-Const-Variablen im globalen Gültigkeitsbereich sind standardmäßig extern. gelten nur **"extern"** , Deklarationen, die die Definition nicht bereitstellen.

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
extern int i;  // declaration only. same as i in FileA

//fileC.cpp
extern int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
extern int i = 43; // same error (extern is ignored on definitions)
```

## <a name="extern-linkage-for-const-globals"></a>externe Verknüpfung für const globals

Ein **const** globale Variable verfügt über interne Verknüpfung in der Standardeinstellung. Wenn Sie die Variable an eine externe Bindung verfügen möchten, wenden Sie die **"extern"** Schlüsselwort, um die Definition als auch über allen anderen Deklarationen in anderen Dateien:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>externe Constexpr-Verknüpfung

In Visual Studio 2017 Version 15.3 und früheren Versionen hat der Compiler immer eine interne Verknüpfung mit "constexpr" Variable auch, wenn die Variable "extern" markiert wurde. In Visual Studio 2017 Version 15.5 ermöglicht ein neuer Compilerschalter ([/Zc:extern7Constexpr](../build/reference/zc-externconstexpr.md)) das richtige standardkonforme Verhalten. Letztendlich wird dies die Standardeinstellung sein.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Wenn eine Headerdatei eine Variable deklariert Extern "constexpr" enthält, muss es markiert sein **__declspec(selectany)** um ordnungsgemäß auf ihre doppelten Deklarationen kombiniert haben:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>Extern "C" und "extern", "C++" Funktionsdeklarationen

In C++ wird bei der Verwendung mit einer Zeichenfolge **"extern"** gibt an, dass die Konventionen der Bindung einer anderen Sprache für die bindungskonventionen verwendet werden. Auf C-Funktionen und - Daten kann nur dann zugegriffen werden, wenn sie zuvor wie eine C-Bindung deklariert wurden. Allerdings müssen sie in einer separat kompilierten Übersetzungseinheit definiert sein.

Microsoft C++ unterstützt die Zeichenfolgen **"C"** und **"C++"** in die *Zeichenfolgenliteral* Feld. Alle Standardincludedateien verwenden enthalten die **"extern"** "C"-Syntax, um die Funktionen der Laufzeit-Bibliothek in C++-Programmen verwendet werden können.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie den Namen zu deklarieren, die C-Verknüpfung haben:

```cpp
// Declare printf with C linkage.
extern "C" int printf(const char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
extern "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
extern "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions
//  ShowChar and GetChar with C linkage.
extern "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

extern "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
extern "C" int errno;
```

Wenn eine Funktion über mehr als eine Verknüpfungsspezifikation verfügt, müssen sie übereinstimmen. Es ist ein Fehler, Funktionen sowohl mit C- als auch mit C++-Bindung zu deklarieren. Wenn darüber hinaus zwei Deklarationen für eine Funktion in einem Programm auftreten – eine mit einer Verknüpfungsspezifikation und eine ohne – muss die Deklaration mit der Verknüpfungsspezifikation die erste sein. Alle redundanten Deklarationen von Funktionen, die bereits eine Verknüpfungsspezifikation haben, erhalten die in der ersten Deklaration angegebene Bindung. Zum Beispiel:

```cpp
extern "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
extern "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Programm und Verknüpfung](program-and-linkage-cpp.md)<br/>
[Extern-Speicherklassenspezifizierer in C](../c-language/extern-storage-class-specifier.md)<br/>
[Verhalten von Bezeichnern in C](../c-language/behavior-of-identifiers.md)<br/>
[Verknüpfung in C](../c-language/linkage.md)