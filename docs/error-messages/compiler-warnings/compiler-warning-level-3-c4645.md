---
title: Compilerwarnung (Stufe 3) C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: a3e5c834a3f14b9a125176dcddd5bcc355cf1faa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401643"
---
# <a name="compiler-warning-level-3-c4645"></a>Compilerwarnung (Stufe 3) C4645

Eine Funktion, die mit "__declspec(noreturn)" deklariert wurde, hat eine Rückgabeanweisung

A [return](../../cpp/return-statement-in-program-termination-cpp.md) -Anweisung wurde in einer Funktion gefunden, die mit dem [noreturn](../../cpp/noreturn.md) `__declspec` -Modifizierer gekennzeichnet ist. Die `return` -Anweisung wurde ignoriert.

Im folgenden Beispiel wird C4645 generiert:

```
// C4645.cpp
// compile with:  /W3
void __declspec(noreturn) func() {
   return;   // C4645, delete this line to resolve
}

int main() {
}
```