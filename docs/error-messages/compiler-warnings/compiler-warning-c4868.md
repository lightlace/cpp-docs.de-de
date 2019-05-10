---
title: Compilerwarnung C4868
ms.date: 10/26/2017
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
ms.openlocfilehash: 72700091fcd22271e6913228a1206b3d5efcbdef
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447176"
---
# <a name="compiler-warning-level-4-c4868"></a>Compilerwarnung C4868 (Stufe 4)

> "_Datei_(*Line_number*)' Compiler kann nicht erzwingen die Auswertungsreihenfolge von links nach rechts in der Initialisiererliste

Die Elemente von einer Initialisiererliste sind in der Reihenfolge von links nach rechts ausgewertet werden soll. Es gibt zwei Fälle, in dem der Compiler kann nicht garantiert diese Reihenfolge ist: die erste ist, wenn einige der Elemente als Wert übergebene Objekte sind die zweite ist beim Kompilieren mit `/clr` und einige Elemente sind Elemente des Arrays oder Felder von Objekten sind. Wenn der Compiler nicht, links-nach-rechts-Evaluierung garantieren kann gibt es Warnung C4868 aus.

Diese Warnung kann infolge einer konformitätsverbesserung für Compiler generiert werden, die für Visual Studio 2015 Update 2 durchgeführt wurde. Code, der kompiliert vor Visual Studio 2015 Update 2 kann jetzt C4868 generieren.

Diese Warnung ist standardmäßig deaktiviert. Verwendung `/Wall` um diese Warnung zu aktivieren.

Um diese Warnung zu beheben, sollten Sie zunächst überlegen Sie, ob links-nach-rechts-Auswertung der Listenelemente Initialisierer ist erforderlich, z. B. wenn die Auswertung der Elemente Nebeneffekte für die Reihenfolge wichtig erzeugen kann. In vielen Fällen muss die Reihenfolge, in der Elemente ausgewertet werden, nicht erkennbare Auswirkungen.

Wenn die Reihenfolge der Auswertung links-nach-rechts-sein muss, überlegen Sie, ob es möglich ist, übergeben die Elemente von `const` stattdessen verweisen. Eine Änderung wie dies beseitigt die Warnung in das folgende Codebeispiel.

## <a name="example"></a>Beispiel

In diesem Beispiel wird die C4868 generiert, und zeigt, wie Sie diesen Fehler beheben:

```cpp
// C4868.cpp
// compile with: /c /Wall
#include <cstdio>

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x): x(x) {}

    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)
    {
        printf("Constructing %d\n", h.x);
    }
};

class TripWarning4868
{
public:
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}

    // This variation will not trigger the warning:
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}
};

int main()
{
    HasCopyConstructor a{1};
    HasCopyConstructor b{2};

    // the warning will indicate the below line, the usage of the braced initializer list.
    TripWarning4868 warningOnThisLine{a, b};
};
```