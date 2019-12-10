---
title: Compilerwarnung (Stufe 3) C4570
ms.date: 11/04/2016
f1_keywords:
- C4570
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
ms.openlocfilehash: 13767cdbd34c72953568181c15ad33119bf5179a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991932"
---
# <a name="compiler-warning-level-3-c4570"></a>Compilerwarnung (Stufe 3) C4570

"Type": ist nicht explizit als abstrakt deklariert, hat jedoch abstrakte Funktionen.

Ein Typ, der [abstrakte](../../extensions/abstract-cpp-component-extensions.md) Funktionen enthält, sollte selbst als abstrakt markiert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4570 generiert.

```cpp
// C4570.cpp
// compile with: /clr /W3 /c
ref struct X {   // C4570
// try the following line instead
// ref class X abstract {
   virtual void f() abstract;
};
```
