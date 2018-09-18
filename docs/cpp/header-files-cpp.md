---
title: Headerdateien (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- header files [C++]
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d1e477b04421f7e8920bba47b2eba4e73df34cb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028531"
---
# <a name="header-files-c"></a>Headerdateien (C++)

Die Namen der Programmelemente, z. B. Variablen, Funktionen, Klassen usw. müssen deklariert werden, bevor sie verwendet werden können. Angenommen, Sie können nicht schreiben `x = 42` ohne dass die Deklaration 'X'.

```cpp
int x; // declaration
x = 42; // use x
```

Weist den Compiler an, ob die Deklaration ist eine **Int**, **doppelte**, **Funktion**, **Klasse** oder einige andere Sache.  Darüber hinaus muss jeder Name (direkt oder indirekt) in alle cpp-Datei deklariert werden in dem es verwendet wird. Wenn Sie ein Programm kompilieren, wird jede cpp-Datei unabhängig voneinander in einer Kompilierungseinheit kompiliert. Der Compiler hat keine Kenntnis welche Namen im anderen Kompilierungseinheiten deklariert werden. Das heißt, wenn Sie eine Klasse oder Funktion oder globale Variable definieren, müssen Sie eine Deklaration, dass wir diesen in jeder zusätzlichen cpp-Datei angeben, der verwendet wird. Jede Deklaration das erledigt ist, muss in allen Dateien genau identisch sein. Inkonsistenz bei eine kleine verursacht Fehler oder unerwartetem Verhalten, wenn der Linker versucht, alle Kompilierungseinheiten in einem einzelnen Programm zusammenzuführen.

Um potenzielle Fehler zu minimieren, hat sich C++ durchgesetzt, die Konvention für die Verwendung *Headerdateien* Deklarationen enthalten. Sie stellen die Deklarationen in einer Headerdatei verwenden und dann die #include-Direktive in alle cpp-Datei oder anderen Headerdatei erfordert diese Deklaration. Die #include-Anweisung fügt eine Kopie der Header-Datei direkt in der CPP-Datei vor der Kompilierung.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine gängige Methode zum Deklarieren Sie eine Klasse, und klicken Sie dann in einer anderen Quelldatei verwenden. Wir beginnen mit der Headerdatei `my_class.h`. Enthält eine Definition einer Klasse, aber beachten Sie, dass die Definition nicht vollständig ist; die Memberfunktion `do_something` ist nicht definiert:

```cpp
// my_class.h
namespace N
{
    class my_class
    {
    public:
        void do_something();
    };

}
```

Als Nächstes erstellen Sie eine Implementierungsdatei (in der Regel mit einer .cpp oder eine ähnliche Erweiterung). Wir rufen Sie die Datei my_class.cpp und geben Sie eine Definition für die Element-Deklaration. Fügen wir eine `#include` Direktive für "my_class.h"-Datei, um die My_class Deklaration eingefügt haben an diesem Punkt in der CPP-Datei, und wir sind `<iostream>` , ziehen Sie in der Deklaration für `std::cout`. Beachten Sie, dass die Anführungszeichen werden verwendet, für die Headerdateien im selben Verzeichnis wie die Quelldatei und spitzen Klammern für standard-Bibliothek-Header verwendet werden. Darüber hinaus haben viele standard-Bibliothek-Header keine h- oder eine andere Dateierweiterung.

In der Implementierungsdatei einschließen, können wir optional eine **mit** Anweisung zu vermeiden, qualifizieren Sie jede Erwähnung von "My_class" oder "Cout" mit "N::" oder "std::".  Fügen Sie keine **mit** Anweisungen in Headerdateien!

```cpp
// my_class.cpp
#include "my_class.h" // header in local directory
#include <iostream> // header in standard library

using namespace N;
using namespace std;

void my_class::do_something()
{
    cout << "Doing something!" << endl;
}
```

Nun können wir `my_class` in einer anderen cpp-Datei. Wir #include die Header-Datei, damit der Compiler in der Deklaration abruft. Alle Anforderungen an den Compiler wissen, ist diese My_class ist eine Klasse, die eine öffentliche Memberfunktion aufgerufen wurde `do_something()`.

```cpp
// my_program.cpp
#include "my_class.h"

using namespace N;

int main()
{
    my_class mc;
    mc.do_something();
    return 0;
}
```

Nach Abschluss der Compiler das Kompilieren von einzelnen cpp-Dateien in OBJ-Dateien übergeben die OBJ-Dateien an dem Linker. Wenn der Linker die Objektdateien zusammenführt, sucht es genau eine Definition für My_class; Es ist in der OBJ-Datei, die für my_class.cpp erstellt, und der Buildvorgang erfolgreich ist.

## <a name="include-guards"></a>#Include-Schutz

Header-Dateien in der Regel haben eine *#include-Schutz* oder `#pragma once` Richtlinie, um sicherzustellen, dass sie nicht mehrere Male in einer einzelnen cpp-Datei eingefügt werden.

```cpp
// my_class.h
#ifndef MY_CLASS_H // include guard
#define MY_CLASS_H

namespace N
{
    class my_class
    {
    public:
        void do_something();
    };
}

#endif /* MY_CLASS_H */
```

## <a name="what-to-put-in-a-header-file"></a>Was in einer Headerdatei eingefügt

Da eine Headerdatei potenziell von mehreren Dateien enthalten sein kann, kann nicht es Definitionen enthalten, die mehrere Definitionen mit dem gleichen Namen führen kann. Im folgenden sind nicht zulässig, oder werden als sehr ungültiges Verfahren angesehen:

- Definitionen von integrierten Typen im Namespace oder im globalen Gültigkeitsbereich
- nicht-Inline-Funktionsdefinitionen
- nicht-Const-Variablendefinitionen
- Aggregate-Definitionen
- Unbenannte Namespaces
- using-Anweisungen

Verwenden der **mit** Richtlinie verursacht einen Fehler nicht unbedingt, aber es kann möglicherweise ein Problem verursachen, da es sich bei daraufhin den Namespace in den Bereich in alle cpp-Datei, die direkt oder indirekt diesen Header enthält.

## <a name="sample-header-file"></a>Beispiel-Headerdatei

Das folgende Beispiel zeigt die verschiedenen Arten von Deklarationen und Definitionen, die in einer Headerdatei zulässig sind:

```cpp
#pragma once
#include <vector> // #include directive
#include <string>

namespace N  // namespace declaration
{
    inline namespace P
    {
        //...
    }

    enum class colors : short { red, blue, purple, azure };

    const double PI = 3.14;  // const and constexpr definitions
    constexpr int MeaningOfLife{ 42 };
    constexpr int get_meaning()
    {
        static_assert(MeaningOfLife == 42, "unexpected!"); // static_assert
        return MeaningOfLife;
    }
    using vstr = std::vector<int>;  // type alias
    extern double d; // extern variable

#define LOG   // macro definition

#ifdef LOG   // conditional compilation directive
    void print_to_log();
#endif

    class my_class   // regular class definition,
    {                // but no non-inline function definitions

        friend class other_class;
    public:
        void do_something();   // definition in my_class.cpp
        inline void put_value(int i) { vals.push_back(i); } // inline OK

    private:
        vstr vals;
        int i;
    };

    struct RGB
    {
        short r{ 0 };  // member initialization
        short g{ 0 };
        short b{ 0 };
    };

    template <typename T>  // template definition
    class value_store
    {
    public:
        value_store<T>() = default;
        void write_value(T val)
        {
            //... function definition OK in template
        }
    private:
        std::vector<T> vals;
    };

    template <typename T>  // template declaration
    class value_widget;
}
```