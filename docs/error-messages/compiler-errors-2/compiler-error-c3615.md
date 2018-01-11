---
title: Compilerfehler Fehler C3615 | Microsoft Docs
ms.date: 10/24/2017
ms.technology: cpp-tools
ms.topic: error-reference
f1_keywords: C3615
dev_langs: C++
helpviewer_keywords: C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea5502ee6e66cf3add4a4ff97e4922a66712ed70
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3615"></a>Compilerfehler Fehler C3615

> Constexpr-Funktion "*Funktion*" kann nicht in einem konstanten Ausdruck führen

Die Funktion *Funktion* konnte nicht ausgewertet werden, als `constexpr` zum Zeitpunkt der Kompilierung. Werden `constexpr`, eine Funktion aufrufen kann nur andere `constexpr` Funktionen.

## <a name="example"></a>Beispiel

Visual Studio-2017 ordnungsgemäß löst einen Fehler aus, wenn der linke Operand einen bedingten Auswertung Vorgang ungültig ist eine `constexpr` Kontext. Der folgende Code kompiliert wird, in Visual Studio 2015, aber nicht im Visual Studio-2017.

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

Um dieses Problem zu beheben, deklarieren Sie entweder die `array::size()` Funktion wie `constexpr` oder Entfernen der `constexpr` aus `f`.