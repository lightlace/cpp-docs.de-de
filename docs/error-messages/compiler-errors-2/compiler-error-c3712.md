---
title: Compilerfehler C3712
ms.date: 11/04/2016
f1_keywords:
- C3712
helpviewer_keywords:
- C3712
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
ms.openlocfilehash: 0b84f4562dcc0dd5dcc3ecb647316772efab6b38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328405"
---
# <a name="compiler-error-c3712"></a>Compilerfehler C3712

"Method": eine Ereignishandlermethode muss denselben Typ wie die Quelle "Methode" zurückgeben

Sie definiert eine Ereignishandlermethode, die nicht den gleichen Typ wie die Quell-Methode zurückgegeben wurde. Um diesen Fehler zu beheben, geben Sie der Ereignishandlermethode denselben Rückgabetyp wie die Quell-Methode.

Im folgende Beispiel wird die C3712 generiert:

```
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