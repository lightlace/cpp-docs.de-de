---
title: Compilerwarnung (Stufe 1) C4305
ms.date: 01/17/2018
f1_keywords:
- C4305
helpviewer_keywords:
- C4305
ms.openlocfilehash: dc718e5f7ebe9478ed1bf2a7323db940935cb1d6
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926120"
---
# <a name="compiler-warning-level-1-c4305"></a>Compilerwarnung (Stufe 1) C4305

> '*context*': Abschneiden von '*Typ1*' zu '*Typ2*'

## <a name="remarks"></a>Hinweise

Diese Warnung wird ausgegeben, wenn ein Wert in einer Initialisierung oder als Konstruktorargument in einen kleineren Typ konvertiert wird, was zu einem Verlust von Informationen führt.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt zwei Möglichkeiten, wie Sie diese Warnung sehen können:

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

Um dieses Problem zu beheben, initialisieren Sie mit einem Wert des richtigen Typs, oder verwenden Sie eine explizite Umwandlung in den richtigen Typ. Verwenden Sie beispielsweise ein **float** -Literalformat wie z. b. 2.71828 f anstelle eines **Double** -Werts (der Standardtyp für Gleit Komma Literale), um eine **float** -Variable zu initialisieren oder an einen Konstruktor zu übergeben, der ein **float** -Argument annimmt.
