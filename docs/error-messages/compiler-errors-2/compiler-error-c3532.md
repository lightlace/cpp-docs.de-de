---
title: Compilerfehler C3532 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3532
dev_langs:
- C++
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25562a83845690cf923784ee27e20fd109c1c832
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109638"
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