---
title: Quellcodeorganisation (C++-Vorlagen)
ms.date: 11/04/2016
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
ms.openlocfilehash: 94e386b6301519b98b101adfca699b7f3128e3c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330999"
---
# <a name="source-code-organization-c-templates"></a>Quellcodeorganisation (C++-Vorlagen)

Eine Klassenvorlage definiert haben, müssen Sie den Quellcode so organisieren, dass die Elementdefinitionen für den Compiler sichtbar sind, wenn er benötigt.   Sie haben die Möglichkeit der Verwendung der *Aufnahme Modell* oder *explizite Instanziierung* Modell. Im Modell einschließen fügen Sie die Element-Definitionen in jeder Datei, die eine Vorlage verwendet wird. Dieser Ansatz ist am einfachsten und bietet maximale Flexibilität im Hinblick auf, welche konkreten Typen zusammen mit der Vorlage verwendet werden können. Der Nachteil besteht darin, dass es die Kompilierungszeiten erhöhen kann. Die Auswirkungen können ins Gewicht, wenn ein Projekt sein, bzw. die eingeschlossenen Dateien selbst sind umfangreich. Mit dem Ansatz explizite Instanziierung instanziiert die Vorlage selbst konkrete Klassen oder Klassenmember für bestimmte Typen.  Dieser Ansatz kann die Kompilierungszeiten beschleunigen, aber er begrenzt die Nutzung nur die Klassen, die die Vorlage-Implementierung voraus aktiviert hat. Im Allgemeinen empfehlen wir, dass Sie das Modell für die Aufnahme verwenden, es sei denn, die Kompilierungszeiten denen zu einem Problem werden.

## <a name="background"></a>Hintergrund

Vorlagen sind nicht wie normale Klassen in dem Sinne, dass der Compiler keinen Objektcode für eine Vorlage oder eines seiner Member verursacht. Es gibt nichts zu generieren, wenn die Vorlage mit konkreten Typen instanziiert wird. Wenn der Compiler findet eine Vorlageninstanziierung wie z. B. `MyClass<int> mc;` und keine Klasse mit dieser Signatur noch vorhanden, wird eine neue Klasse generiert. Es versucht auch zum Generieren von Code für alle Memberfunktionen, die verwendet werden. Wenn diese Definitionen in einer Datei befinden, die nicht #included, direkt oder indirekt in der CPP-Datei, die kompiliert wird, der Compiler nicht sichtbar.  Aus Sicht des Compilers ist dies nicht unbedingt ein Fehler, da die Funktionen in einer anderen Übersetzungseinheit, definiert werden können, in denen Fall der Linker diese finden.  Wenn Sie diesen Code durch der Linker nicht gefunden wird, löst es eine **nicht aufgelöste externe** Fehler.

## <a name="the-inclusion-model"></a>Das Modell einschließen

Die einfachste und am häufigsten verwendete Möglichkeit um Vorlagendefinitionen in einer Übersetzungseinheit sichtbar zu machen, ist die Definitionen in der Headerdatei selbst platzieren.  Jede cpp-Datei, die die Vorlage wird verwendet, muss einfach #include Sie den Header. Dies ist der Ansatz, der in der Standardbibliothek verwendet.

```cpp
#ifndef MYARRAY
#define MYARRAY
#include <iostream>

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    // Full definitions:
    MyArray(){}
    void Print()
    {
        for (const auto v : arr)
        {
            std::cout << v << " , ";
        }
    }

    T& operator[](int i)
   {
       return arr[i];
   }
};
#endif
```

Bei diesem Ansatz wird der Compiler hat Zugriff auf die vollständige Vorlage, und Sie können Vorlagen bei Bedarf für jeden Typ zu instanziieren. Es ist einfach und relativ einfach zu verwalten. Allerdings muss das Modell einschließen Kosten im Hinblick auf die Kompilierung.   Diese Kosten können in großen Programmen besonders wichtig, insbesondere dann, wenn die Vorlagenheader selbst #includes anderen Header. Jede cpp-Dateien, die #includes Header erhält eine eigene Kopie der Vorlagen und alle Definitionen. Der Linker in der Regel werden Dinge klären, sodass Sie werden nicht am Ende mehrere Definitionen für eine Funktion, aber dauert einige Zeit, um diese Aufgabe übernimmt. Zu kleineren Programmen, dass zusätzliche Kompilierungszeit wahrscheinlich nicht relevant ist.

## <a name="the-explicit-instantiation-model"></a>Das Modell für die explizite Instanziierung

Wenn das Modell für die Aufnahme nicht auf Ihr Projekt ist und man definitiv den Satz von Typen, die zum Instanziieren einer Vorlage verwendet werden, können Sie den Vorlagencode in eine h- und CPP-Datei zu trennen und in der CPP-Datei explizit instanziieren die Vorlagen. Dies bewirkt Objektcode generiert werden, dass der Compiler bei der gefundenen Benutzer Instanziierungen angezeigt wird.

Sie erstellen eine explizite Instanziierung mit der Schlüsselwort-Vorlage, gefolgt von der Signatur der Entität, die instanziiert werden soll. Dies kann ein Typ oder Member sein. Wenn Sie einen Typ explizit instanziiert werden, werden alle Mitglieder instanziiert.

```cpp
template MyArray<double, 5>;
```

```cpp
//MyArray.h
#ifndef MYARRAY
#define MYARRAY

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    MyArray();
    void Print();
    T& operator[](int i);
};
#endif

//MyArray.cpp
#include "stdafx.h"
#include <iostream>
#include "MyArray.h"

using namespace std;

template<typename T, size_t N>
MyArray<T,N>::MyArray(){}

template<typename T, size_t N>
void MyArray<T,N>::Print()
{
    for(const auto v : arr)
    {
        cout << v << "'";
    }
    cout << endl;
}

template MyArray<double, 5>;template MyArray<string, 5>;
```

Im vorherigen Beispiel wird der expliziten Instanziierungen am unteren Rand der CPP-Datei sind. Ein `MyArray` kann verwendet werden, nur für **doppelte** oder `String` Typen.

> [!NOTE]
> In C ++ 11 die **exportieren** Schlüsselwort wurde im Kontext des Vorlagendefinitionen als veraltet markiert. In der Praxis hat dies nur eine geringe Auswirkung, da die meisten Compiler nicht unterstützt.