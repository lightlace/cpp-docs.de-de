---
title: Compilerfehler C3854
ms.date: 11/04/2016
f1_keywords:
- C3854
helpviewer_keywords:
- C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
ms.openlocfilehash: 8c62117e9437233f614aa0e57a3848fcb8dd0c79
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754848"
---
# <a name="compiler-error-c3854"></a>Compilerfehler C3854

Ausdruck auf der linken Seite von "=" ergibt eine Funktion. Eine Zuweisung zu einer Funktion ist nicht möglich (eine Funktion ist kein l-Wert).

Ein Verweis kann nicht erneut initialisiert werden. Das dereferenzieren eines Verweises auf eine Funktion ergibt eine Funktion, bei der es sich um einen Rvalue handelt, dem Sie nicht zugewiesen werden können. Daher können Sie nicht über einen Verweis auf eine Funktion zuweisen.

Im folgenden Beispiel wird C3854 generiert:

```cpp
// C3854.cpp
int afunc(int i)
{
   return i;
}

typedef int (& rFunc_t)(int);
typedef int (* pFunc_t)(int);

int main()
{
   rFunc_t rf = afunc;   // OK binding a reference to function
   pFunc_t pf = &afunc;   // OK initializing a pointer to function

   *pf = &afunc;   // C3854
   // try the following line instead
   // pf = &afunc;
   *rf = &afunc;   // C3854
}
```
