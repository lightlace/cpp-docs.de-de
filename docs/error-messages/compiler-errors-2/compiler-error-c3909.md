---
title: Compilerfehler C3909
ms.date: 11/04/2016
f1_keywords:
- C3909
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
ms.openlocfilehash: 69613a1058bd5178ea4c03931664dd00bad7a101
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748995"
---
# <a name="compiler-error-c3909"></a>Compilerfehler C3909

die awinrt-oder die verwaltete Ereignis Deklaration muss in einem WinRT-oder verwalteten Typ auftreten.

Ein Windows-Runtime-Ereignis oder verwaltetes Ereignis wurde in einem systemeigenen Typ deklariert. Deklarieren Sie zum Beheben dieses Fehlers Ereignisse in Windows-Runtime-Typen oder verwalteten Typen.

Weitere Informationen finden Sie unter [Event](../../extensions/event-cpp-component-extensions.md).

Im folgenden Beispiel wird C3909 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C3909.cpp
// compile with: /clr /c
delegate void H();
class X {
   event H^ E;   // C3909 - use ref class X instead
};

ref class Y {
   static event H^ E {
      void add(H^) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```
