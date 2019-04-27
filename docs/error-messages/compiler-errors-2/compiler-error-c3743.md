---
title: Compilerfehler C3743
ms.date: 11/04/2016
f1_keywords:
- C3743
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
ms.openlocfilehash: 137913e0c6909712cbb6745666112d315925ab0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226855"
---
# <a name="compiler-error-c3743"></a>Compilerfehler C3743

Hook/unhook kann nur auf eine gesamte Schnittstelle angewendet werden, wenn der "Layout_dependent"-Parameter des Event_receiver "true" ist.

Die [__unhook](../../cpp/unhook.md) Funktion unterscheidet sich hinsichtlich der die Anzahl von Parametern, die basierend auf den übergebenen Wert die `layout_dependent` Parameter in der [Event_receiver](../../windows/event-receiver.md) Klasse.

Im folgende Beispiel wird die C3743 generiert:

```
// C3743.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[module(name="xx")];
[object] __interface I { HRESULT f(); };

[event_receiver(com, layout_dependent=true), coclass]
struct R : I {
        HRESULT f() {
      return 0;
   }
        R() {
   }

   R(I* a) {
      __hook(I, a, &R::f);   // C3743
      // The following line resolves the error.
      // __hook(I, a);
   }
};
```