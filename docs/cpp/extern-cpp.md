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
ms.openlocfilehash: d42a32202f7fa67751ea36757c13b2c6af4953b2
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301534"
---
# <a name="extern-c"></a>extern (C++)

Das **extern** -Schlüsselwort wird auf eine globale Variable, eine Funktion oder eine Vorlagen Deklaration angewendet, um anzugeben, dass der Name dieses Objekts eine *externe Verknüpfung*aufweist. Hintergrundinformationen über Verknüpfungen und Gründe für die Verwendung von globalen Variablen finden Sie unter [Übersetzungseinheiten und Verknüpfungen](program-and-linkage-cpp.md).

Das **extern** -Schlüsselwort hat abhängig vom Kontext vier Bedeutungen:

1. in einer nicht konstanten globalen Variablen Deklaration gibt **extern** an, dass die Variable oder Funktion in einer anderen Übersetzungseinheit definiert ist. Der **externe** muss in allen Dateien, mit Ausnahme derjenigen, in der die Variable definiert ist, angewendet werden.
1. in einer Konstanten Variablen Deklaration gibt Sie an, dass die Variable eine externe Verknüpfung aufweist. Der **externe** muss auf alle Deklarationen in allen Dateien angewendet werden. (Die globalen Konstanten Variablen haben standardmäßig interne Verknüpfungen.)
1. **extern "C"** gibt an, dass die Funktion an anderer Stelle definiert ist und die Aufruf Konvention der C-Sprache verwendet. Der externe "C"-Modifizierer kann auch auf mehrere Funktions Deklarationen in einem-Block angewendet werden.
1. in einer Vorlagen Deklaration gibt Sie an, dass die Vorlage bereits an anderer Stelle instanziiert wurde. Dies ist eine Optimierung, die dem Compiler mitteilt, dass die andere Instanziierung wieder verwendet werden kann, anstatt eine neue Instanz am aktuellen Speicherort zu erstellen. Weitere Informationen zu dieser Verwendung von **extern**finden Sie unter [Vorlagen](templates-cpp.md).

## <a name="extern-linkage-for-non-const-globals"></a>extern Verknüpfungen für nicht konstante globale Werte

Wenn der Linker **extern** vor einer globalen Variablen Deklaration sieht, sucht er nach der Definition in einer anderen Übersetzungseinheit. Deklarationen von nicht konstanten Variablen im globalen Gültigkeitsbereich sind standardmäßig extern. wenden Sie nur **extern** auf die Deklarationen an, die die Definition nicht bereitstellen.

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

## <a name="extern-linkage-for-const-globals"></a>externe Verknüpfung für konstante Globals

Eine **Konstante** globale Variable verfügt standardmäßig über interne Verknüpfungen. Wenn die Variable eine externe Verknüpfung aufweisen soll, müssen Sie das **extern** -Schlüsselwort auf Definition und alle anderen Deklarationen in anderen Dateien anwenden:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>externe constexpr-Verknüpfung

In Visual Studio 2017 Version 15,3 und früher gab der Compiler immer eine interne constexpr-Variable, auch wenn die Variable als extern markiert war. In Visual Studio 2017 Version 15.5 ermöglicht ein neuer Compilerschalter ([/Zc:extern7Constexpr](../build/reference/zc-externconstexpr.md)) das richtige standardkonforme Verhalten. Letztendlich wird dies die Standardeinstellung sein. Die/permissive--Option aktiviert/Zc: externconstexpr nicht.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Wenn eine Header Datei eine Variable enthält, die extern als "constexpr" deklariert ist, muss Sie als **__declspec (selectany)** gekennzeichnet werden, damit die doppelten Deklarationen ordnungsgemäß kombiniert werden können:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>externe "C"-und externC++-Funktions Deklarationen

In C++gibt **extern** bei Verwendung mit einer Zeichenfolge an, dass die Verknüpfungs Konventionen einer anderen Sprache für die Deklaratoren verwendet werden. Auf C-Funktionen und - Daten kann nur dann zugegriffen werden, wenn sie zuvor wie eine C-Bindung deklariert wurden. Allerdings müssen sie in einer separat kompilierten Übersetzungseinheit definiert sein.

Microsoft C++ unterstützt die Zeichen folgen **"C"** und **C++""** im Feld *Zeichenfolgenliteral.* Alle standardmäßigen Includedateien verwenden die **externe** "C"-Syntax, damit die Lauf Zeit Bibliotheksfunktionen in C++ Programmen verwendet werden können.

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

Wenn eine Funktion über mehr als eine Verknüpfungsspezifikation verfügt, müssen sie übereinstimmen. Es ist ein Fehler, Funktionen sowohl mit C- als auch mit C++-Bindung zu deklarieren. Wenn darüber hinaus zwei Deklarationen für eine Funktion in einem Programm auftreten – eine mit einer Verknüpfungsspezifikation und eine ohne – muss die Deklaration mit der Verknüpfungsspezifikation die erste sein. Alle redundanten Deklarationen von Funktionen, die bereits eine Verknüpfungsspezifikation haben, erhalten die in der ersten Deklaration angegebene Bindung. Beispiel:

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

[Stichwörter](../cpp/keywords-cpp.md)<br/>
[Übersetzungseinheiten und Verknüpfungen](program-and-linkage-cpp.md)<br/>
[Speicherklassenspezifizierer "extern" in C](../c-language/extern-storage-class-specifier.md)<br/>
[Verhalten von bezeichlern in C](../c-language/behavior-of-identifiers.md)<br/>
[Verknüpfung in C](../c-language/linkage.md)