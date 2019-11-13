---
title: Compilerwarnung (Stufe 1) C4807
ms.date: 11/04/2016
f1_keywords:
- C4807
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
ms.openlocfilehash: c18dbac0681067d9bc52455dfdbe44a24c786ee7
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051544"
---
# <a name="compiler-warning-level-1-c4807"></a>Compilerwarnung (Stufe 1) C4807

"Operation": Unsichere Kombination von Typ "Typ" und signiertem Bitfeld des Typs "Typ"

Diese Warnung wird erzeugt, wenn ein vorzeichenbehaftetes Bitfeld der Länge 1 mit einer `bool` -Variablen verglichen wird. Da ein vorzeichenbehaftetes Bitfeld der Länge 1 nur die Werte -1 oder 0 enthalten kann, ist der Vergleich mit einem `bool`-Wert nicht unproblematisch. Keine Warnungen werden dagegen erzeugt, wenn `bool` -Werte mit vorzeichenlosen Bitfeldern der Länge 1 verglichen werden, da diese mit `bool` identisch sind und nur 0 oder 1 enthalten können.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4807 generiert:

```cpp
// C4807.cpp
// compile with: /W1
typedef struct bitfield {
   signed mybit : 1;
} mybitfield;

int main() {
   mybitfield bf;
   bool b = true;

   // try..
   // int b = true;

   bf.mybit = -1;
   if (b == bf.mybit) {   // C4807
      b = false;
   }
}
```