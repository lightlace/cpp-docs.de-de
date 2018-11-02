---
title: Compilerfehler C3910
ms.date: 11/04/2016
f1_keywords:
- C3910
helpviewer_keywords:
- C3910
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
ms.openlocfilehash: b9194149c532044f6c8a1eab84729f7896f1352b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568544"
---
# <a name="compiler-error-c3910"></a>Compilerfehler C3910

'Ereignis': müssen Member 'Methode' definieren

Ein Ereignis definiert wurde, aber enthielt nicht die angegebene, erforderliche Accessor-Methode.

Weitere Informationen finden Sie unter [Ereignis](../../windows/event-cpp-component-extensions.md).

Im folgende Beispiel wird die C3910 generiert:

```
// C3910.cpp
// compile with: /clr /c
delegate void H();
ref class X {
   event H^ E {
      // uncomment the following lines
      // void add(H^) {}
      // void remove( H^ h ) {}
      // void raise( ) {}
   };   // C3910

   event H^ E2; // OK data member
};
```