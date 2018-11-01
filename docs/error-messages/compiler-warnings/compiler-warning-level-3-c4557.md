---
title: Compilerwarnung (Stufe 3) C4557
ms.date: 11/04/2016
f1_keywords:
- C4557
helpviewer_keywords:
- C4557
ms.assetid: 7d9db716-03b2-4ee5-9b09-ba8aa5aa7e4c
ms.openlocfilehash: 5b236559708759cb30487ef9a8fde92cc42889c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608619"
---
# <a name="compiler-warning-level-3-c4557"></a>Compilerwarnung (Stufe 3) C4557

'__assume' enthält den Effekt 'Effekt'

Der an übergebene Wert eine [__assume](../../intrinsics/assume.md) Anweisung2 geändert wurde.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgende Beispiel wird die C4557 generiert:

```
// C4557.cpp
// compile with: /W3
#pragma warning(default : 4557)
int main()
{
   int i;
   __assume(i++);   // C4557
}
```