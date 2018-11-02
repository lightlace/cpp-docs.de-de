---
title: Compilerfehler C3900
ms.date: 11/04/2016
f1_keywords:
- C3900
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
ms.openlocfilehash: d031b55407d108b4f8be362156911bfae688326a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512358"
---
# <a name="compiler-error-c3900"></a>Compilerfehler C3900

'Member': im aktuellen Bereich nicht zulässig.

Eigenschaftenblöcken können Funktionsdeklarationen und nur Inlinefunktionsdefinitionen enthalten. Keine Mitglieder als Funktionen sind in Eigenschaftenblöcken zulässig. Es dürfen keine Typdefinitionen, Operatoren oder Friend-Funktionen. Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).

Ereignisdefinitionen können nur Zugriff auf Methoden und Funktionen enthalten.

Im folgende Beispiel wird die C3900 generiert:

```
// C3900.cpp
// compile with: /clr
ref class X {
   property int P {
      void set(int);   // OK
      int i;   // C3900 variable declaration
   };
};
```

Im folgende Beispiel wird die C3900 generiert:

```
// C3900b.cpp
// compile with: /clr
using namespace System;
delegate void H();
ref class X {
   event H^ E {
      int m;   // C3900

      // OK
      void Test() {}

      void add( H^ h ) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```