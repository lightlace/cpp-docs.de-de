---
title: Compilerfehler C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: a140847b642ac2437b67aa957328c3b8fbfc592d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761568"
---
# <a name="compiler-error-c3536"></a>Compilerfehler C3536

"Symbol": kann nicht verwendet werden, bevor es initialisiert wird.

Das oben dargestellte Symbol kann nicht verwendet werden, bevor es initialisiert wird. In der Praxis bedeutet dies, dass eine Variable nicht verwendet werden kann, um sich selbst zu initialisieren.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Initialisieren Sie keine Variable mit sich selbst.

## <a name="example"></a>Beispiel

Das folgende Beispiel ergibt C3536, da jede Variable mit sich selbst initialisiert wird.

```cpp
// C3536.cpp
// Compile with /Zc:auto
int main()
{
   auto a = a;     //C3536
   auto b = &b;    //C3536
   auto c = c + 1; //C3536
   auto* d = &d;   //C3536
   auto& e = e;    //C3536
   return 0;
};
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)
