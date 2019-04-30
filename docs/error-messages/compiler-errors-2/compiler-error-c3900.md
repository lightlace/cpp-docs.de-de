---
title: Compilerfehler C3900
ms.date: 11/04/2016
f1_keywords:
- C3900
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
ms.openlocfilehash: 35df94ccfcd7942f9057cb37ceee349c09b80607
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345407"
---
# <a name="compiler-error-c3900"></a>Compilerfehler C3900

'Member': im aktuellen Bereich nicht zulässig.

Eigenschaftenblöcken können Funktionsdeklarationen und nur Inlinefunktionsdefinitionen enthalten. Keine Mitglieder als Funktionen sind in Eigenschaftenblöcken zulässig. Es dürfen keine Typdefinitionen, Operatoren oder Friend-Funktionen. Weitere Informationen finden Sie unter [property](../../extensions/property-cpp-component-extensions.md).

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