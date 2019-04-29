---
title: Compilerfehler C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: dd4368faaf323a75116128ec3a47666260436fce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397418"
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