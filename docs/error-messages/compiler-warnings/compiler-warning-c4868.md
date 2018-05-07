---
title: Compilerfehler Warnung C4868 | Microsoft Docs
ms.date: 10/26/2017
ms.topic: error-reference
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 922a1a8434da8449758b9d55ebe89ace2f262cd5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4868"></a>Compilerwarnung (Stufe 4) C4868

> "_Datei_(*Line_number*)" Compiler kann die Reihenfolge der Auswertung von links nach rechts in der Initialisiererliste nicht erzwingen

Die Elemente einer Initialisiererliste werden in Reihenfolge von links nach rechts ausgewertet werden. Es gibt zwei Fälle, die der Compiler in der Lage, diese Sortierung zu gewährleisten kann: die erste ist, wenn bestimmte Elemente der Objekte, die als Wert übergeben werden Das zweite ist beim Kompilieren mit `/clr` und einige Elemente sind Elemente des Arrays oder Feldern von Objekten sind. Wenn der Compiler nicht, links-nach-rechts-Evaluation garantieren kann gibt es Warnung C4868.

Diese Warnung kann infolge einer konformitätsverbesserung generiert werden, die für Visual C++ 2015 Update 2 vorgenommen wurde. Code, der kompiliert vor Visual C++ 2015 Update 2 kann jetzt C4868 generieren.

Diese Warnung ist standardmäßig deaktiviert. Verwendung `/Wall` um diese Warnung zu aktivieren.

Um diese Warnung zu beheben, zuerst überlegen Sie, ob links-nach-rechts die Auswertung von Listenelementen Initialisierer ist erforderlich, z. B. wenn Auswertung der Elemente Reihenfolge abhängiges Nebeneffekte erzeugen kann. In vielen Fällen ist die Reihenfolge, in der Elemente ausgewertet werden, Observable keinen Einfluss.

Wenn die Reihenfolge der Auswertung links-nach-rechts-sein muss, zu überlegen, ob es möglich ist, übergeben die Elemente von `const` stattdessen verweisen. Eine Änderung wie diese entfällt die Warnung im folgenden Codebeispiel.

## <a name="example"></a>Beispiel

In diesem Beispiel wird die C4868 generiert, und zeigt eine Möglichkeit, sie diesen Fehler beheben:

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