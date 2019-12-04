---
title: Compilerfehler C3662
ms.date: 11/04/2016
f1_keywords:
- C3662
helpviewer_keywords:
- C3662
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
ms.openlocfilehash: 48fe8bd4a6872ff214d185ac77553debab78ab20
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758189"
---
# <a name="compiler-error-c3662"></a>Compilerfehler C3662

'Member': Der Überschreibungsspezifizierer 'Spezifizierer' ist nur für Memberfunktionen von verwalteten oder WinRT-Klassen zulässig.

Ein Überschreibungsspezifizierer wurde für einen Member des systemeigenen Typs verwendet, was nicht zulässig ist.

Weitere Informationen finden Sie unter [explizite über](../../extensions/explicit-overrides-cpp-component-extensions.md)schreibungen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3662 generiert:

```cpp
// C3662.cpp
// compile with: /clr /c
struct S {
   virtual void f();
};

struct S1 : S {
   virtual void f() new;   // C3662
};

ref struct T {
   virtual void f();
};

ref struct T1 : T {
   virtual void f() new;   // OK
};
```
