---
title: Compilerwarnung (Stufe 1) C4602
ms.date: 11/04/2016
f1_keywords:
- C4602
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
ms.openlocfilehash: 7cacadea560dc5a68d396ac607deb3a5a3c236ee
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965911"
---
# <a name="compiler-warning-level-1-c4602"></a>Compilerwarnung (Stufe 1) C4602

\#Pragma pop_macro: "Makro Name" kein vorheriger #Pragma push_macro für diesen Bezeichner.

Wenn Sie [pop_macro](../../preprocessor/pop-macro.md) für ein bestimmtes Makro verwenden, müssen Sie zunächst den entsprechenden Makronamen an [push_macro](../../preprocessor/push-macro.md)übergeben. Im folgenden Beispiel wird C4602 generiert:

```cpp
// C4602.cpp
// compile with: /W1
int main()
{
   #pragma pop_macro("x")   // C4602 x is not on the stack
}
```