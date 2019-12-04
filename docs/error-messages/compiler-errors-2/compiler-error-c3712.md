---
title: Compilerfehler C3712
ms.date: 11/04/2016
f1_keywords:
- C3712
helpviewer_keywords:
- C3712
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
ms.openlocfilehash: 51772f22f83cff5c602bd2310d7913c0d317ba66
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753366"
---
# <a name="compiler-error-c3712"></a>Compilerfehler C3712

"Method": eine Ereignishandlermethode muss denselben Typ wie die Quelle "Method" zurückgeben.

Sie haben eine Ereignishandlermethode definiert, die nicht denselben Typ wie die Quell Ereignismethode zurückgegeben hat. Um diesen Fehler zu beheben, geben Sie der Ereignishandlermethode denselben Rückgabetyp wie der Quell Ereignismethode.

Im folgenden Beispiel wird C3712 generiert:

```cpp
// C3712.cpp
// compile with: /c
[event_source(native)]
class CEventSrc {
public:
   __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   int handler1() { return 0; }
   // try the following line instead
   // void handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712
   }
   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712
   }
};
```
