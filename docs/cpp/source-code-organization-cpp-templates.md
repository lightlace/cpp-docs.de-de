---
title: Source Code Organisation (C++-Vorlagen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 1b3b17c17bad3834774f747548dda6710e178cb4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="source-code-organization-c-templates"></a>Code Quellorganisation (C++-Vorlagen)

Eine Klassenvorlage definieren, müssen Sie den Quellcode so organisieren, dass die Elementdefinitionen für den Compiler sichtbar sind, wenn er benötigt.   Sie haben die Wahl der Verwendung der *Aufnahme Modell* oder *explizite Instanziierung* Modell. Im Modell einschließen fügen Sie die Definitionen der Elemente in jeder Datei, die mithilfe einer Vorlage. Dieser Ansatz ist am einfachsten und bietet maximale Flexibilität im Hinblick auf welche konkreten Typen zusammen mit der Vorlage verwendet werden können. Der Nachteil ist, dass es Kompilierungszeiten erhöhen kann. Die Auswirkung kann sein bedeutsam werden, wenn ein Projekt und/oder die eingeschlossenen Dateien selbst werden große. Mit dem Ansatz explizite Instanziierung instanziiert die Vorlage selbst konkrete Klassen oder Klassenmember für bestimmte Typen.  Dieser Ansatz kann die Kompilierungszeiten beschleunigen, aber dies beschränkt die Nutzung, um nur die Klassen, die Vorlage Implementierer voraus aktiviert hat. Im Allgemeinen wird empfohlen, dass das Modell aufgenommen verwenden, es sei denn, die Kompilierungszeiten ein Problem werden.  
  
## <a name="background"></a>Hintergrund

 Vorlagen sind nicht wie normale Klassen in dem Sinne, dass der Compiler Code für eine Vorlage oder eines seiner Member des Objekts nicht generiert. Es ist nichts zu generieren, wenn die Vorlage mit konkrete Typen instanziiert wird. Wenn der Compiler erkennt eine Vorlageninstanziierung wie z. B. `MyClass<int> mc;` und keine Klasse mit dieser Signatur noch vorhanden ist, wird eine neue Klasse generiert. Es wird versucht auch zum Generieren von Code für alle Memberfunktionen, die verwendet werden. Wenn diese Definitionen in einer Datei befinden, die nicht #included ist, direkt oder indirekt in der CPP-Datei, die kompiliert wird, der Compiler kann nicht angezeigt werden.  Aus Sicht des Compilers ist dies nicht unbedingt ein Fehler, da die Funktionen in einer anderen Übersetzungseinheit definiert werden können, in denen Sie Fall der Linker erwarten kann.  Wenn Sie diesen Code in der Linker nicht gefunden wird, löst ein **nicht aufgelösten externen** Fehler.  

## <a name="the-inclusion-model"></a>Das Modell einschließen

 Die einfachste und häufigste Möglichkeit, Vorlagendefinitionen innerhalb einer Übersetzungseinheit sichtbar machen darin, die Definitionen in der Headerdatei selbst.  Alle cpp-Datei, die die Vorlage verwendet muss einfach #include Header. Dies ist der Ansatz, der in der Standardbibliothek verwendet.  
  
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
  
 Bei diesem Ansatz wird der Compiler hat Zugriff auf die vollständige Vorlagendefinition und Vorlagen bei Bedarf für jeden Typ instanziiert werden kann. Es ist einfach und relativ leicht zu warten. Das Modell einschließen müssen jedoch im Hinblick auf Kompilierungszeiten Kosten.   Diese Kosten kann in großen Programmen signifikant sein insbesondere dann, wenn die Vorlagenheader selbst #includes andere Header. Alle cpp-Datei mit #includes Header erhält eine eigene Kopie der Funktionsvorlagen und alle Definitionen. Der Linker wird im Allgemeinen Dinge sortieren sodass Sie werden nicht am Ende mehrere Definitionen für eine Funktion, aber es Zeit ist, um diese Aufgaben auszuführen. sein. In kleineren Programme, die zusätzliche Kompilierungszeit wahrscheinlich nicht relevant ist.  
  
## <a name="the-explicit-instantiation-model"></a>Die explizite Instanziierung-Modell

 Wenn das Modell einschließen nicht gültig für das Projekt ist, und kennen definitiv den Satz von Typen, die zum Instanziieren einer Vorlage verwendet werden, können Sie Aussondern den Vorlagencode in eine h- und CPP-Datei und in der CPP-Datei die Vorlagen explizit instanziieren. Dies bewirkt Objektcode generiert werden, dass der Compiler angezeigt werden, wenn Benutzer Instanziierungen gefunden wird.  
  
 Erstellen Sie eine explizite Instanziierung mithilfe der Schlüsselwort-Vorlage, gefolgt von der Signatur der Entität, die Sie instanziieren möchten. Dies kann ein Typ oder Member sein. Wenn Sie einen Typ explizit instanziiert werden, werden alle Elemente instanziiert.  
  
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
  
 Im vorherigen Beispiel werden die keine expliziten Instanziierungen am unteren Rand der CPP-Datei. Ein `MyArray` kann verwendet werden, nur für **doppelte** oder **Zeichenfolge** Typen.  
  
> [!NOTE]
>  In C ++ 11 die **exportieren** Schlüsselwort wurde im Kontext der Vorlagendefinitionen veraltet. Praktisch hat dies nur eine geringe Auswirkung, da die meisten Compiler nie unterstützt.
