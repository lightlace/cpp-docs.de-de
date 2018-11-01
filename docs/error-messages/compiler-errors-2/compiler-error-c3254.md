---
title: Compilerfehler C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 7e051c6c44d3b85f6f3faaf5380ecf54cba5d73c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470667"
---
# <a name="compiler-error-c3254"></a>Compilerfehler C3254

"explizite Überschreibung": Klasse enthält die explizite Überschreibung "Override", jedoch nicht von abgeleitet ist, eine Schnittstelle, die die Funktionsdeklaration enthält

Wenn Sie [explizit überschreiben](../../cpp/explicit-overrides-cpp.md) eine Methode, Klasse, die die Überschreibung enthält muss abgeleitet werden, direkt oder indirekt, überschreiben Sie aus der Typ, der die Funktion enthält.

Im folgende Beispiel wird die C3254 generiert:

```
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```