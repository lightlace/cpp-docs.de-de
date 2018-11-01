---
title: Compilerfehler C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: 0b342f8b878c48a77336fab4921cf4a668e248ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607050"
---
# <a name="compiler-error-c2462"></a>Compilerfehler C2462

'Bezeichner': Typdefinition in "new-Ausdruck" nicht möglich

Sie können keinen Typ definieren, in dem Operandenfeld, der die `new` Operator. Fügen Sie die Typdefinition in einer separaten Anweisung.

Im folgende Beispiel wird die C2462 generiert:

```
// C2462.cpp
int main() {
   new struct S { int i; };   // C2462
}
```