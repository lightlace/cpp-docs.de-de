---
title: Compilerwarnung (Stufe 1) C4305
ms.date: 1/17/2018
f1_keywords:
- C4305
helpviewer_keywords:
- C4305
ms.openlocfilehash: 3f9116b0e7bdd9ee13c42b48f44da4b090f41ccd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649123"
---
# <a name="compiler-warning-level-1-c4305"></a>Compilerwarnung (Stufe 1) C4305

> "*Kontext*': Verkürzung von '*type1*'to'*Typ2*"

## <a name="remarks"></a>Hinweise

Diese Warnung wird ausgegeben, wenn ein Wert in einen kleineren Typ in einer Initialisierung oder als Konstruktorargument, was zu einem Verlust von Informationen konvertiert wird.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt zwei Möglichkeiten, die Sie möglicherweise diese Warnung angezeigt:

```cpp
// C4305.cpp
// Compile by using: cl /EHsc /W4 C4305.cpp

struct item
{
    item(float) {}
};

int main()
{
    float f = 2.71828;          // C4305 'initializing'
    item i(3.14159);            // C4305 'argument'
    return static_cast<int>(f);
}
```

Um dieses Problem zu beheben, initialisieren Sie, indem Sie mit einem Wert den richtigen Typ aufweist, oder verwenden Sie eine explizite Umwandlung in den richtigen Typ. Beispielsweise verwenden eine **"float"** wie z. B. 2.71828f anstelle von literalen eine **doppelte** (dem Standardtyp für gleitkommaliterale) zum Initialisieren eine **"float"** Variable oder Übergabe an eine Konstruktor, eine **"float"** Argument.
