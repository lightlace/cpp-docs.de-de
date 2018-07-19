---
title: "\"extern\" (C++) | Microsoft Docs"
ms.custom: ''
ms.date: 04/12/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- extern
- extern_CPP
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00b9f94d02443163f45b83d64702fe49622597cd
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261057"
---
# <a name="extern-c"></a>"extern" (C++)

Die **"extern"** Schlüsselwort wird angewendet, um eine globale Variable, Funktion oder Vorlage-Deklaration, um anzugeben, dass der Name des Objekts, diese wurde *externe Verknüpfung*. Hintergrundinformationen zu Verknüpfungen und warum die Verwendung von globalen Variablen abgeraten wird, finden Sie unter [Programm und Verknüpfung](program-and-linkage-cpp.md).

Die **"extern"** Schlüsselwort hat vier Bedeutungen je nach Kontext:

1. in einer globalen Variablen nicht Const-Deklaration **"extern"** gibt an, dass die Variable oder Funktion in einer anderen Übersetzungseinheit definiert ist. Die **"extern"** muss angewendet werden, in allen Dateien mit Ausnahme der, in dem die Variable definiert ist.
1. in einer Variablendeklaration const ist wird angegeben, dass die Variable eine externe Verknüpfung hat. Die **"extern"** muss auf allen Deklarationen in allen Dateien angewendet werden. (Globale const-Variablen eine interne Bindung haben standardmäßig.)
1. **Extern "C"** gibt an, dass die Funktion an anderer Stelle definiert ist und die Programmiersprache C-Aufrufkonvention verwendet. Extern "C"-Modifizierer kann auch auf mehrere Deklarationen in einem Block angewendet werden.
1. in einer Vorlagendeklaration wird angegeben, dass die Vorlage bereits an anderer Stelle instanziiert wurde. Dies ist eine Optimierung, die dem Compiler wird angewiesen, dass sie die anderen Instanziierung auf, anstatt eine neue erstellen, an der aktuellen Position wieder verwenden kann. Weitere Informationen über diese Verwendung von **"extern"**, finden Sie unter [Vorlagen](templates-cpp.md).

## <a name="extern-linkage-for-non-const-globals"></a>Verknüpfung von "extern" für nicht Const-globals

Wenn der Linker sieht **"extern"** vor der Deklaration einer globalen Variablen, sucht Sie nach der Definition in einer anderen Übersetzungseinheit. Deklarationen von nicht Const-Variablen im globalen Gültigkeitsbereich sind standardmäßig extern. gelten nur **"extern"** den Deklarationen, die die Definition nicht bereitstellen.

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

## <a name="extern-linkage-for-const-globals"></a>Verknüpfung von "extern" für const globals

Ein **const** (globale Variable) standardmäßig über interne Verknüpfung verfügt. Wenn Sie die Variable an eine externe Bindung aufweisen soll, gelten die **"extern"** Schlüsselwort für die Definition als auch auf allen anderen Deklarationen in anderen Dateien:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>"Extern" Constexpr-Verknüpfung

In Visual Studio-2017 Version 15,3 und früher hat der Compiler immer eine Constexpr-Variable interne-Verknüpfung selbst, wenn die Variable "extern" markiert wurde. In Visual Studio 2017 Version 15.5 ermöglicht ein neuer Compilerschalter ([/Zc:extern7Constexpr](../build/reference/zc-externconstexpr.md)) das richtige standardkonforme Verhalten. Letztendlich wird dies die Standardeinstellung sein.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Wenn eine Headerdatei eine Variable deklariert "extern" Constexpr enthält, muss er markiert sein **__declspec(selectany)** ordnungsgemäß seiner doppelten Deklarationen, die kombiniert werden sollen:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>Extern "C" und "extern", "C++" Funktionsdeklarationen

 In C++ wird bei Verwendung mit einer Zeichenfolge **"extern"** gibt an, dass für die bindungskonventionen einer anderen Sprache verwendet werden. Auf C-Funktionen und - Daten kann nur dann zugegriffen werden, wenn sie zuvor wie eine C-Bindung deklariert wurden. Allerdings müssen sie in einer separat kompilierten Übersetzungseinheit definiert sein.

 Microsoft C++ unterstützt die Zeichenfolgen **"C"** und **"C++"** in der *Zeichenfolgenliteral* Feld. Alle Standardincludedateien umfassen die Verwendung von Dateien die **"extern"** "C"-Syntax auf die Laufzeit-Bibliothekscode-Funktionen in C++-Programmen verwendet werden können.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Namen zu deklarieren, die C-Verknüpfung haben:

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

- [Schlüsselwörter](../cpp/keywords-cpp.md)
- [Programm und Verknüpfung](program-and-linkage-cpp.md)
- ["extern" Speicherklassenspezifizierer in C](../c-language/extern-storage-class-specifier.md) 
- [Verhalten von Bezeichnern in C](../c-language/behavior-of-identifiers.md) 
- [Verknüpfung in C](../c-language/linkage.md)