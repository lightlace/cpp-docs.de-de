---
title: Compilerwarnung (Stufe 3) C4570
ms.date: 11/04/2016
f1_keywords:
- C4570
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
ms.openlocfilehash: 1c92bd7f632ea6662c3cee1bcaa1dd0c917fb2a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661304"
---
# <a name="compiler-warning-level-3-c4570"></a>Compilerwarnung (Stufe 3) C4570

'Typ': ist nicht explizit als abstrakte jedoch abstrakte Funktionen weist deklariert

Ein Typ, der enthält [abstrakte](../../windows/abstract-cpp-component-extensions.md) Funktionen sollten sich selbst als abstrakt gekennzeichnet werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4570 generiert.

```
// C4570.cpp
// compile with: /clr /W3 /c
ref struct X {   // C4570
// try the following line instead
// ref class X abstract {
   virtual void f() abstract;
};
```