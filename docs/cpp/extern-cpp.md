---
title: extern (C++)
description: Leitfaden zum C++ sprach extern-Schlüsselwort.
ms.date: 01/28/2020
f1_keywords:
- extern
- extern_CPP
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
no-loc:
- extern
- const
- constexpr
- permissive
ms.openlocfilehash: 422b6960802c59f1c45e0c22a4a85988c808a5b3
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821765"
---
# <a name="opno-locextern-c"></a>extern (C++)

Das **extern** -Schlüsselwort kann auf eine globale Variable, eine Funktion oder eine Vorlagen Deklaration angewendet werden. Gibt an, dass das Symbol eine *externe Verknüpfung*aufweist. Hintergrundinformationen über Verknüpfungen und Gründe für die Verwendung von globalen Variablen finden Sie unter [Übersetzungseinheiten und Verknüpfungen](program-and-linkage-cpp.md).

Das **extern** -Schlüsselwort hat abhängig vom Kontext vier Bedeutungen:

- In einer nicht **const** globalen Variablen Deklaration gibt **extern** an, dass die Variable oder Funktion in einer anderen Übersetzungseinheit definiert ist. Der **extern** muss in allen Dateien angewendet werden, mit Ausnahme derjenigen, in der die Variable definiert ist.

- In einer **const** Variablen Deklaration gibt Sie an, dass die Variable eine externe Verknüpfung aufweist. Der **extern** muss auf alle Deklarationen in allen Dateien angewendet werden. (Globale **const** Variablen haben standardmäßig eine interne Verknüpfung.)

- **extern "C"** gibt an, dass die Funktion an anderer Stelle definiert ist und die Aufruf Konvention der C-Sprache verwendet. Der extern "C"-Modifizierer kann auch auf mehrere Funktions Deklarationen in einem-Block angewendet werden.

- In einer Vorlagen Deklaration gibt **extern** an, dass die Vorlage bereits an einem anderen Speicherort instanziiert wurde. **extern** weist den Compiler an, dass die andere Instanziierung wieder verwendet werden kann, anstatt eine neue zu erstellen, die sich am aktuellen Speicherort befindet. Weitere Informationen zur Verwendung von **extern** finden Sie unter [explizite Instanziierung](explicit-instantiation.md).

## <a name="opno-locextern-linkage-for-non-opno-locconst-globals"></a>extern Verknüpfung für nichtconst Globals

Wenn der Linker **extern** vor einer globalen Variablen Deklaration sieht, sucht er nach der Definition in einer anderen Übersetzungseinheit. Deklarationen von nicht **const** Variablen im globalen Gültigkeitsbereich sind standardmäßig extern. Wenden Sie **extern** nur auf die Deklarationen an, die die Definition nicht bereitstellen.

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

## <a name="opno-locextern-linkage-for-opno-locconst-globals"></a>extern Verknüpfung für const Globals

Eine **const** globale Variable verfügt standardmäßig über interne Verknüpfungen. Wenn die Variable eine externe Verknüpfung aufweisen soll, wenden Sie das **extern** -Schlüsselwort auf die Definition und alle anderen Deklarationen in anderen Dateien an:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="opno-locextern-opno-locconstexpr-linkage"></a>extern constexpr Verknüpfung

In Visual Studio 2017 Version 15,3 und früher gab der Compiler immer eine **constexpr** Variable Internal-Verknüpfung, auch wenn die Variable als **extern** markiert war. In Visual Studio 2017 Version 15,5 und höher ermöglicht der [/Zc: externconstexpr](../build/reference/zc-externconstexpr.md) -Compilerschalter ein korrektes Standardverhalten. Schließlich wird die Option zum Standardwert. Die Option " [/permissive-](../build/reference/permissive-standards-conformance.md) " aktiviert nicht **/Zc: externconstexpr**.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Wenn eine Header Datei eine Variable enthält, die **extern** **constexpr** deklariert ist, muss Sie als `__declspec(selectany)` gekennzeichnet werden, damit die doppelten Deklarationen ordnungsgemäß kombiniert werden:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="opno-locextern-c-and-opno-locextern-c-function-declarations"></a>extern "C"-und externC++""-Funktions Deklarationen

Bei C++Verwendung mit einer Zeichenfolge gibt **extern** an, dass die Verknüpfungs Konventionen einer anderen Sprache für die Deklaratoren verwendet werden. Auf c-Funktionen und-Daten kann nur zugegriffen werden, wenn Sie zuvor als c-Verknüpfung deklariert wurden. Allerdings müssen sie in einer separat kompilierten Übersetzungseinheit definiert sein.

Microsoft C++ unterstützt die Zeichen folgen **"C"** und **C++""** im Feld *Zeichenfolgenliteral.* Alle standardmäßigen Includedateien verwenden die **extern "C"** -Syntax, damit die Lauf Zeit Bibliotheksfunktionen in C++ Programmen verwendet werden können.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Namen mit C-Verknüpfung deklariert werden:

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

Wenn eine Funktion über mehr als eine Verknüpfungs Spezifikation verfügt, müssen Sie zustimmen. Es ist ein Fehler, Funktionen als "C" und C++ "Verknüpfung" zu deklarieren. Wenn darüber hinaus zwei Deklarationen für eine Funktion in einem Programm auftreten – eine mit einer Verknüpfungsspezifikation und eine ohne – muss die Deklaration mit der Verknüpfungsspezifikation die erste sein. Alle redundanten Deklarationen von Funktionen, die bereits eine Verknüpfungsspezifikation haben, erhalten die in der ersten Deklaration angegebene Bindung. Beispiel:

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

[Stichwörter](../cpp/keywords-cpp.md)\
[Übersetzungseinheiten und Verknüpfungs](program-and-linkage-cpp.md)\
[extern Speicherklassenspezifizierer in C](../c-language/extern-storage-class-specifier.md)\
[Verhalten von bezeichlern in C](../c-language/behavior-of-identifiers.md) -\
[Verknüpfung in C](../c-language/linkage.md)
