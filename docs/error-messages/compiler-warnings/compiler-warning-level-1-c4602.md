---
title: Compilerwarnung (Stufe 1) C4602
ms.date: 11/04/2016
f1_keywords:
- C4602
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
ms.openlocfilehash: c719ae23ed3799debf2db9c8f2d82b3c49db3156
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430387"
---
# <a name="compiler-warning-level-1-c4602"></a>Compilerwarnung (Stufe 1) C4602

\#Pragma-Pop_macro: 'Makroname' kein vorherigen #pragma Push_macro für diesen Bezeichner

Wenn Sie [pop_macro](../../preprocessor/pop-macro.md) für ein bestimmtes Makro verwenden, müssen Sie zunächst den entsprechenden Makronamen an [push_macro](../../preprocessor/push-macro.md)übergeben. Im folgenden Beispiel wird C4602 generiert:

```
// C4602.cpp
// compile with: /W1
int main()
{
   #pragma pop_macro("x")   // C4602 x is not on the stack
}
```