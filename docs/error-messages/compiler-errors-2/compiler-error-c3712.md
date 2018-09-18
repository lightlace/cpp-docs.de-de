---
title: Compilerfehler C3712 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3712
dev_langs:
- C++
helpviewer_keywords:
- C3712
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa1790c2f5634f01d52e0eec65f5bfcf933ab058
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029922"
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