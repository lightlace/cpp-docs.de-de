---
title: Compilerwarnung (Stufe 3) C4570
ms.date: 11/04/2016
f1_keywords:
- C4570
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
ms.openlocfilehash: fd144847ce6c4f8697cd866d304c23cb9b2be408
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188876"
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