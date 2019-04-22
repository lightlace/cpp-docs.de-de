---
title: Compilerfehler C3532
ms.date: 11/04/2016
f1_keywords:
- C3532
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
ms.openlocfilehash: 7b5d1fe61ae08811186e25547ccc3f33e3b0198e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023970"
---
# <a name="compiler-error-c3532"></a>Compilerfehler C3532

"Type": falsche Verwendung von 'Auto'

Der angegebene Typ kann nicht deklariert werden, mit der `auto` Schlüsselwort. Beispielsweise können keine der `auto` Schlüsselwort, um ein Array oder eine Methode deklarieren Typ zurückgeben.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Stellen Sie sicher, dass der Initialisierungsausdruck einen gültigen Typ ergibt.

1. Stellen Sie sicher, dass Sie ein Array oder einen Rückgabetyp der Methode nicht deklarieren.

## <a name="example"></a>Beispiel

Im folgende Beispiel C3532 erzeugt, da die `auto` Schlüsselwort kann nicht der Rückgabetyp einer Methode deklariert.

```
// C3532a.cpp
// Compile with /Zc:auto
auto f(){}   // C3532
```

## <a name="example"></a>Beispiel

Im folgende Beispiel C3532 erzeugt, da die `auto` Schlüsselwort kann kein Array zu deklarieren.

```
// C3532b.cpp
// Compile with /Zc:auto
int main()
{
   int x[5];
   auto a[5];            // C3532
   auto b[1][2];         // C3532
   auto y[5] = x;        // C3532
   auto z[] = {1, 2, 3}; // C3532
   auto w[] = x;         // C3532
   return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)