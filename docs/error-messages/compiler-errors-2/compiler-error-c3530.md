---
title: Compilerfehler C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 3766eaa83457ba6cffaf8b1599983a065772911c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750142"
---
# <a name="compiler-error-c3530"></a>Compilerfehler C3530

"Auto" kann nicht mit einem anderen Typspezifizierer kombiniert werden.

Ein Typspezifizierer wird mit dem `auto`-Schlüsselwort verwendet.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Verwenden Sie keinen Typspezifizierer in einer Variablen Deklaration, die das `auto`-Schlüsselwort verwendet.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3530 erzeugt, da Variable `x` sowohl mit dem Schlüsselwort `auto` als auch mit dem Typ `int`deklariert wird und da das Beispiel mit **/Zc: Auto**kompiliert wird.

```cpp
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
