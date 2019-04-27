---
title: Compilerfehler C3891
ms.date: 11/04/2016
f1_keywords:
- C3891
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
ms.openlocfilehash: 74b8802a165ab3265cc0f1c6a0b33b31d3db401d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62281559"
---
# <a name="compiler-error-c3891"></a>Compilerfehler C3891

"Var": Ein literal-Datenmember kann nicht als l-Wert verwendet werden

Ein [literal](../../extensions/literal-cpp-component-extensions.md) -Variable ist eine Konstante, und der Wert kann nicht geändert werden, nachdem es in der Deklaration initialisiert wurde.

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