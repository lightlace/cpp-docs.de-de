---
title: Compilerfehler C3909
ms.date: 11/04/2016
f1_keywords:
- C3909
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
ms.openlocfilehash: 435288ba657bd22ba29c6681014ae15baa051cec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636461"
---
# <a name="compiler-error-c3909"></a>Compilerfehler C3909

aWinRT oder verwaltete Ereignisdeklaration muss in einem WinRT oder verwalteten Typ auftreten.

Ein Windows-Runtime-Ereignis oder verwaltetes Ereignis wurde in einem systemeigenen Typ deklariert. Deklarieren Sie zum Beheben dieses Fehlers Ereignisse in Windows-Runtime-Typen oder verwalteten Typen.

Weitere Informationen finden Sie unter [Ereignis](../../windows/event-cpp-component-extensions.md).

Im folgenden Beispiel wird C3909 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
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