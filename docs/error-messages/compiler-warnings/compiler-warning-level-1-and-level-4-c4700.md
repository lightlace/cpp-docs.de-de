---
title: Compilerwarnung (Stufe 1 und Stufe 4) C4700 | Microsoft Docs
ms.custom: 
ms.date: 02/21/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4700
dev_langs:
- C++
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00b871d6199338cc3040d6bddedb85f8732dfccd
ms.sourcegitcommit: 4e416049665819ac62f5300ddf86e94adede4ba0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>Compilerwarnung (Stufe 1 und Stufe 4) C4700

> nicht initialisierten lokalen Variablen '*Namen*"verwendet

Die lokale Variable *Namen* wurde *verwendet*, d. h. aus lesen, bevor er hat ein Wert zugewiesen wurde. In C und C++ sind lokale Variablen in der Standardeinstellung nicht initialisiert. Nicht initialisierte Variablen können einen beliebigen Wert enthalten, und ihre Verwendung führt zu nicht definiertem Verhalten. Warnung C4700 gibt fast immer einen Fehler, der in Ihrem Programm zu unvorhersehbaren Ergebnissen führt oder Abstürze verursachen kann.

Um dieses Problem zu beheben, können Sie lokale Variablen zu initialisieren, wenn sie deklariert werden, oder weisen einen Wert zu werden, bevor sie verwendet werden. Eine Funktion kann verwendet werden, zum Initialisieren einer Variablenverweis, die als Verweisparameter übergeben wird, oder wenn seine Adresse als Zeigerparameter übergeben wird.

## <a name="example"></a>Beispiel

In diesem Beispiel wird C4700 generiert, wenn Variablen t, u und v verwendet werden, bevor sie initialisiert wird, und zeigt die Art des Garbage-Werts, die auftreten können. Variablen x-, y- und z führen, die die Warnung nicht zu verursachen, da sie vor der Verwendung initialisiert werden:

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

Wenn dieser Code ausführen, t, u und v ist nicht initialisiert werden, und die Ausgabe für s kann nicht berechnet werden:

```Output
Value in s: 37816963
Value in w: 42
```
