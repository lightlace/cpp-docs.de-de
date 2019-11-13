---
title: Compilerwarnung (Stufe 1) C4600
ms.date: 11/04/2016
f1_keywords:
- C4600
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
ms.openlocfilehash: 6eae37d006b5fcd6bd1c5e2993f1752c0534ee45
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966225"
---
# <a name="compiler-warning-level-1-c4600"></a>Compilerwarnung (Stufe 1) C4600

\#Pragma "Makro Name": Es wurde eine gültige nicht leere Zeichenfolge erwartet.

Es ist nicht möglich, eine leere Zeichenfolge anzugeben, wenn Sie einen Makronamen per Push oder Pop entweder mit dem [pop_macro](../../preprocessor/pop-macro.md) oder [push_macro](../../preprocessor/push-macro.md).

Im folgenden Beispiel wird C4600 generiert:

```cpp
// C4600.cpp
// compile with: /W1
int main()
{
   #pragma push_macro("")   // C4600 passing an empty string
}
```