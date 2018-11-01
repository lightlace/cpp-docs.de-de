---
title: Compilerfehler C3891
ms.date: 11/04/2016
f1_keywords:
- C3891
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
ms.openlocfilehash: 67d12984a32998c244bcd04f99a5f2200a192974
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524565"
---
# <a name="compiler-error-c3891"></a>Compilerfehler C3891

"Var": Ein literal-Datenmember kann nicht als l-Wert verwendet werden

Ein [literal](../../windows/literal-cpp-component-extensions.md) -Variable ist eine Konstante, und der Wert kann nicht geändert werden, nachdem es in der Deklaration initialisiert wurde.

Im folgende Beispiel wird die C3891 generiert:

```
// C3891.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3891
}
```