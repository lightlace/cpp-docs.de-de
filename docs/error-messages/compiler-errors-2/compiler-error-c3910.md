---
title: Compilerfehler C3910
ms.date: 11/04/2016
f1_keywords:
- C3910
helpviewer_keywords:
- C3910
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
ms.openlocfilehash: 186cd67d77e9aafbfe6a7d9dc18afb2bdbd94f0c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768808"
---
# <a name="compiler-error-c3910"></a>Compilerfehler C3910

'Ereignis': müssen Member 'Methode' definieren

Ein Ereignis definiert wurde, aber enthielt nicht die angegebene, erforderliche Accessor-Methode.

Weitere Informationen finden Sie unter [Ereignis](../../extensions/event-cpp-component-extensions.md).

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