---
title: Compilerwarnung (Stufe 3) C4646
ms.date: 11/04/2016
f1_keywords:
- C4646
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
ms.openlocfilehash: a5f78a978baa1c5b4c7854692d7b8b6ff294f3a2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991722"
---
# <a name="compiler-warning-level-3-c4646"></a>Compilerwarnung (Stufe 3) C4646

Eine Funktion, die mit "__declspec(noreturn)" deklariert wurde, hat einen nicht leeren Rückgabetyp

Eine mit dem [noreturn](../../cpp/noreturn.md) `__declspec` -Modifizierer gekennzeichnete Funktion muss den [void](../../cpp/void-cpp.md) -Rückgabetyp aufweisen.

Im folgenden Beispiel wird C4646 generiert:

```cpp
// C4646.cpp
// compile with: /W3 /WX
int __declspec(noreturn) TestFunction()
{   // C4646  make return type void
}
```
