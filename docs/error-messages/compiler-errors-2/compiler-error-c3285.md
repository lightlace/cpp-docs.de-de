---
title: Compilerfehler C3285
ms.date: 11/04/2016
f1_keywords:
- C3285
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
ms.openlocfilehash: 6bc211fb2394a9a2989702c13e19bd63ea8a5ad7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381331"
---
# <a name="compiler-error-c3285"></a>Compilerfehler C3285

Die For Each-Anweisung kann nicht bei Variablen vom Typ "Typ" verwendet werden.

Mit der `for each` -Anweisung wird eine Gruppe von eingebetteten Anweisungen für jedes Element in einem Array oder einer Objektauflistung wiederholt.

Weitere Informationen finden Sie unter [for each, in](../../dotnet/for-each-in.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3285 generiert.

```
// C3285.cpp
// compile with: /clr
int main() {
   for each (int i in 0) {}   // C3285

   array<int> ^p = { 1, 2, 3 };
   for each (int j in p) {}   // OK
}
```