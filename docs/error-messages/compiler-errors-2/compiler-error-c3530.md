---
title: Compilerfehler C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 90f6000c7d4c4bfa0d610bd5942df0b958e47c60
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643625"
---
# <a name="compiler-error-c3530"></a>Compilerfehler C3530

'Auto' kann nicht mit einem anderen Typspezifizierer kombiniert werden

Ein Typspezifizierer der Verwendung der `auto` Schlüsselwort.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Verwenden Sie keinen Typspezifizierer in einer Variablendeklaration, die verwendet die `auto` Schlüsselwort.

## <a name="example"></a>Beispiel

Das folgenden Beispiel wird C3530 erzeugt, weil Variablen `x` wird deklariert, mit der `auto` -Schlüsselwort und Typ `int`, und da im Beispiel wird die Kompilierung mit **/Zc: Auto**.

```
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)