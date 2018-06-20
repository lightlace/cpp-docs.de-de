---
title: Headerdateien (C++) | Microsoft Docs
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b571cd2836e66ebef21898af27cf2a6d7082e0e5
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261052"
---
# <a name="header-files-c"></a>Headerdateien (C++)

Die Namen der Programmelemente, z. B. Variablen, Funktionen, Klassen usw. müssen deklariert werden, bevor sie verwendet werden können. Angenommen, Sie können nicht einfach schreiben `x = 42` ohne zuerst deklariert 'X'. 

```cpp
int x; // declaration
x = 42; // use x
```

 Weist den Compiler an, ob die Deklaration ist eine **Int**, **doppelte**, **Funktion**, eine **Klasse** oder eine andere Bedeutung.  Darüber hinaus muss jeder Name (direkt oder indirekt) in jeder cpp-Datei deklariert werden in dem er verwendet wird. Beim Kompilieren eines Programms wird die einzelnen cpp-Dateien in einer Kompilierungseinheit unabhängig kompiliert. Der Compiler hat keine Kenntnis von welchen Namen in anderen Kompilierungseinheiten deklariert werden. Das heißt, wenn Sie eine Klasse oder Funktion oder globale Variable definieren, müssen Sie eine Deklaration des dieses Objekts in jeder zusätzlichen cpp-Datei angeben, die verwendet werden. Jede Deklaration des Objekts, diese muss in allen Dateien identisch sein. Eine leichte Inkonsistenz wird Fehlern oder unerwartetem Verhalten führen, wenn der Linker versucht, alle Kompilierungseinheiten in ein einzelnes Programm zusammenzuführen.

Um potenzielle Fehler zu minimieren, C++ hat üblicherweise angenommen *Headerdateien* Deklarationen enthalten. Sie stellen die Deklarationen in einer Headerdatei, verwenden Sie die #include-Direktive in jeder cpp-Datei oder anderen Headerdatei erfordert diese Deklaration. Die #include-Direktive fügt eine Kopie des Header-Datei direkt in der CPP-Datei vor der Kompilierung. 

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine allgemeine Möglichkeit, deklarieren Sie eine Klasse, und klicken Sie dann in einer anderen Quelldatei verwenden. Wir beginnen mit der Headerdatei **my_class.h**. Sie enthält eine Definition einer Klasse, aber beachten Sie, dass die Definition nicht vollständig ist; die Memberfunktion `do_something` ist nicht definiert:

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

Als Nächstes erstellen Sie eine Implementierungsdatei (i. d. r. mit einem .cpp oder einer ähnlichen Erweiterung). Wir rufen Sie die Datei my_class.cpp und geben Sie eine Definition für die Memberdeklaration. Fügen wir eine `#include` Direktive für "my_class.h"-Datei, um die My_class Deklaration eingefügt haben an diesem Punkt in der CPP-Datei, und wir enthalten  **\<Iostream >** , ziehen Sie in der Deklaration für `std::cout`. Beachten Sie, dass Anführungszeichen sind nach den Headerdateien im selben Verzeichnis wie die Quelldatei verwendet, und spitzen Klammern für standard bibliotheksheader verwendet werden. Darüber hinaus müssen viele Standardbibliothek-Header nicht h- oder eine andere Dateierweiterung.

In der Implementierungsdatei können optional verwenden wir eine **mit** Anweisung zu vermeiden, qualifizieren Sie jede erwähnt "My_class" oder "Cout" mit "N::" oder "std::".  Put nicht **mit** Anweisungen in Headerdateien!

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

Wir können jetzt `my_class` in einer anderen cpp-Datei. Wir #include die Header-Datei, damit der Compiler in der Deklaration abruft. Alle Compiler muss das wissen, ist dieser My_class ist eine Klasse, die eine öffentliche Memberfunktion aufgerufen hat `do_something()`.

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

Nach Abschluss der Compiler Kompilieren von einzelnen cpp-Dateien in der OBJ-Dateien wird die OBJ-Dateien an dem Linker übergeben. Wenn der Linker die Objektdateien zusammenführt findet sie genau eine Definition für My_class; Es ist in der OBJ-Datei für my_class.cpp erstellt, und der Buildvorgang erfolgreich war.

## <a name="include-guards"></a>#Include-Schutz

Header-Dateien in der Regel haben eine *#include-Schutz* oder ein **#pragma einmal** Richtlinie, um sicherzustellen, dass sie nicht mehrere Male in einer einzelnen cpp-Datei eingefügt werden. 

my_class.h
#<a name="ifndef-myclassh--include-guard"></a>Ifndef MY_CLASS_H / / #include-Schutz
#<a name="define-myclassh"></a>Definieren von MY_CLASS_H


Namespace N {-Klasse My_class {öffentliche: "void" do_something();};

}

#<a name="endif--myclassh-"></a>Endif / * MY_CLASS_H * /

## <a name="what-to-put-in-a-header-file"></a>Was, in einer Headerdatei eingefügt werden soll.

Da eine Headerdatei potenziell durch mehrere Dateien enthalten sein kann, darf keine es Definitionen enthalten, die mehrere Definitionen mit demselben Namen erstellen können. Im folgenden sind nicht zulässig, oder sehr nicht üblich gelten:

- integrierte Typdefinitionen Namespace oder im globalen Gültigkeitsbereich
- nicht-Inline-Funktionsdefinitionen 
- nicht Konstante Variable Definitionen
- Aggregate von Definitionen
- Unbenannte Namespaces
- using-Anweisungen

Verwenden der **mit** Richtlinie nicht notwendigerweise verursacht einen Fehler, aber es kann möglicherweise ein Problem verursachen, da daraufhin den Namespace in den Bereich in jeder cpp-Datei, die direkt oder indirekt über diesen Header enthält. 

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
