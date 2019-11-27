---
title: Compilerwarnung (Stufe 4) C4254
ms.date: 11/04/2016
f1_keywords:
- c4254
helpviewer_keywords:
- C4254
ms.assetid: c7dcef24-d535-4c98-bb41-fc3d2b88fd11
ms.openlocfilehash: 33b3ba795acb8c72c7d1630071aa2884b6137464
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541942"
---
# <a name="compiler-warning-level-4-c4254"></a>Compilerwarnung (Stufe 4) C4254

' Operator ': Konvertierung von ' Typ1 ' in ' Typ2 ', möglicher Datenverlust

Einem kleineren Bitfeld wurde ein größeres Bitfeld zugewiesen. Es kann zu Datenverlusten kommen.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4254 generiert:

```cpp
// C4254.cpp
// compile with: /W4
#pragma warning(default: 4254)

struct X {
   int a : 20;
   int b : 12;
};

int main() {
   X *x = new X();
   x->b = 10;
   x->a = 4;
   x->a = x->b;    // OK
   x->b = x->a;    // C4254
};
```