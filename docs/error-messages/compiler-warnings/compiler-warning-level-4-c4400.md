---
title: Compilerwarnung (Stufe 4) C4400
ms.date: 11/04/2016
f1_keywords:
- C4400
helpviewer_keywords:
- C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
ms.openlocfilehash: 61a6d3090355c9bda8aa11c041b302e4ec77ec8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557282"
---
# <a name="compiler-warning-level-4-c4400"></a>Compilerwarnung (Stufe 4) C4400

'Typ': Const/Volatile-Qualifizierer für diesen Typ werden nicht unterstützt.

Die [const](../../cpp/const-cpp.md)und [flüchtige](../../cpp/volatile-cpp.md)Qualifizierer nicht mit den Variablen der Typen der common Language Runtime ausgeführt werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4400 generiert.

```
// C4400.cpp
// compile with: /clr /W4
// C4401 expected
using namespace System;
#pragma warning (disable : 4101)
int main() {
   const String^ str;   // C4400
   volatile String^ str2;   // C4400
}
```