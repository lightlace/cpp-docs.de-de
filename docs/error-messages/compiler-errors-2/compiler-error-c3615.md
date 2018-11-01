---
title: Compilerfehler C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: e966295b5ab63350828ddb73d6791a9e30bb5c59
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652217"
---
# <a name="compiler-error-c3615"></a>Compilerfehler C3615

> Constexpr-Funktion "*Funktion*' kann nicht in einem konstanten Ausdruck ergeben

Die Funktion *Funktion* konnte nicht ausgewertet werden, als `constexpr` zum Zeitpunkt der Kompilierung. Sollen `constexpr`, eine Funktion aufrufen kann nur andere `constexpr` Funktionen.

## <a name="example"></a>Beispiel

Visual Studio 2017 löst ordnungsgemäß einen Fehler, wenn der linke Operand eines bedingten auswertungsvorgangs in ungültig ist eine `constexpr` Kontext. Der folgende Code kompiliert in Visual Studio 2015, aber nicht in Visual Studio 2017.

```cpp
// C3615.cpp
// Compile with: /c

template<int N>
struct myarray
{
    int size() const { return N; }
};

constexpr bool f(const myarray<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615 starting in Visual Studio 2017
}
```

Um dieses Problem zu beheben, deklarieren die `array::size()` fungieren als `constexpr` oder entfernen Sie die `constexpr` aus `f`.