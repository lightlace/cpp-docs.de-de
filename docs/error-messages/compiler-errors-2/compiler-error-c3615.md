---
title: Compilerfehler Fehler C3615 | Microsoft Docs
ms.date: 10/24/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3615
dev_langs:
- C++
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce1ab43f8e15535614cedf43dba42fef882bf87a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253393"
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