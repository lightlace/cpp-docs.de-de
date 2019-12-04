---
title: Compilerfehler C3711
ms.date: 11/04/2016
f1_keywords:
- C3711
helpviewer_keywords:
- C3711
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
ms.openlocfilehash: 7f2414a51321bf249e3ac049a7048f41b71cb856
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753405"
---
# <a name="compiler-error-c3711"></a>Compilerfehler C3711

"Methode": eine nicht verwaltete Ereignis Quell Methode muss "void" oder einen ganzzahligen Typ zurückgeben.

Sie haben in der Ereignis Quelle eine Methode definiert, die nicht "void" oder einen ganzzahligen Typ zurückgegeben hat. Um diesen Fehler zu beheben, stellen Sie fest, dass das Ereignis und der Ereignishandler den Rückgabetyp `void` oder einen ganzzahligen Typ wie `int` oder `long`haben.

Im folgenden Beispiel wird C3711 generiert:

```cpp
// C3711.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[event_source(native)]
class CEventSrc {
public:
   __event float event1();   // C3711
   // try the following line instead
   // __event int event1();
   // also change the handler, below
};

[event_receiver(native)]
class CEventRec {
public:
   float handler1() {         // change float to int
      return 0.0;             // change 0.0 to 0
   }
   void HookEvents(CEventSrc* pSrc) {
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }
   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};

int main() {
}
```
