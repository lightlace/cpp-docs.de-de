---
title: Compilerfehler C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: a16c5bd46d806d09861d5734b637c2c9d9b2f9d0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345491"
---
# <a name="compiler-error-c3536"></a>Compilerfehler C3536

'Symbol': kann nicht verwendet werden, bevor es initialisiert wird

Das angegebene Symbol kann nicht verwendet werden, bevor es initialisiert wird. In der Praxis bedeutet dies, dass eine Variable nicht verwendet werden kann, um sich selbst zu initialisieren.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Initialisieren Sie eine Variable mit sich selbst nicht.

## <a name="example"></a>Beispiel

Im folgende Beispiel C3536 erzeugt, weil jede Variable, mit sich selbst initialisiert wird.

```
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