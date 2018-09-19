---
title: Compilerfehler C3717 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3717
dev_langs:
- C++
helpviewer_keywords:
- C3717
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75c770ecfc914c033c1db71578cda137d632e363
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086696"
---
# <a name="compiler-error-c3717"></a>Compilerfehler C3717

"Method": eine Methode, die Ereignisse auslöst, kann nicht definiert werden

Sie haben eine Ereignismethode, die die Implementierung umfasst deklariert. Ein [__event](../../cpp/event.md) Deklaration der Methode kann keine Definition haben. Um diesen Fehler zu beheben, stellen Sie sicher, dass keine Methode Ereignisdeklarationen Definitionen verfügen. Z. B. in den folgenden Code entfernen den Hauptteil der Funktion aus der `event1` Deklaration wie durch den Kommentaren angegeben.

Im folgende Beispiel wird die C3717 generiert:

```
// C3717.cpp
[event_source(native)]
class CEventSrc {
public:
   __event void event1() {   // C3717
   }

   // remove definition for event1 and substitute following declaration
   // __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void handler1() {
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