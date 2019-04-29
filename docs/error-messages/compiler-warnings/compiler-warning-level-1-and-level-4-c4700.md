---
title: Compilerwarnung (Stufe 1 und Stufe 4) C4700
ms.date: 02/21/2018
f1_keywords:
- C4700
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
ms.openlocfilehash: fa3326bd5ab495dbc4c54130bb168422eb827dce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300295"
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>Compilerwarnung (Stufe 1 und Stufe 4) C4700

> nicht initialisierte lokale Variable "*Namen*" verwendet

Die lokale Variable *Namen* wurde *verwendet*, d. h. lesen, bevor es wurde ein Wert zugewiesen wurde. In C und C++ werden lokale Variablen nicht standardmäßig initialisiert werden. Nicht initialisierte Variablen können einen beliebigen Wert enthalten, und ihre Verwendung zu nicht definiertem Verhalten führt. Warnung C4700 weist fast immer auf einen Fehler, der in Ihrem Programm zu unvorhersehbaren Ergebnissen oder Abstürze verursachen können.

Um dieses Problem zu beheben, können Sie lokale Variablen zu initialisieren, wenn sie deklariert werden, oder weisen einen Wert zu werden, bevor sie verwendet werden. Eine Funktion kann verwendet werden, um eine Variable zu initialisieren, die als Verweisparameter übergeben wird, oder wenn die Adresse als Parameter für einen Zeiger übergeben wird.

## <a name="example"></a>Beispiel

In diesem Beispiel wird C4700 generiert, wenn Variablen t, u und v verwendet werden, bevor sie initialisiert werden, und zeigt die Arten der Garbage-Wert, der zur Folge haben kann. Variablen X, y und z führen, die die Warnung nicht zu verursachen, da sie vor der Verwendung initialisiert werden:

```cpp
// c4700.cpp
// compile by using: cl /EHsc /W4 c4700.cpp
#include <iostream>

// function takes an int reference to initialize
void initialize(int& i)
{
    i = 21;
}

int main()
{
    int s, t, u, v;   // Danger, uninitialized variables

    s = t + u + v;    // C4700: t, u, v used before initialization
    std::cout << "Value in s: " << s << std::endl;

    int w, x;         // Danger, uninitialized variables
    initialize(x);    // fix: call function to init x before use
    int y{10};        // fix: initialize y, z when declared
    int z{11};        // This C++11 syntax is recommended over int z = 11;

    w = x + y + z;    // Okay, all values initialized before use
    std::cout << "Value in w: " << w << std::endl;
}
```

Wenn dieser Code ausführen, t, u und v ist nicht initialisiert werden, und die Ausgabe für s ist unvorhersehbar:

```Output
Value in s: 37816963
Value in w: 42
```
