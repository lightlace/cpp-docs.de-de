---
title: Compilerfehler C3717
ms.date: 11/04/2016
f1_keywords:
- C3717
helpviewer_keywords:
- C3717
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
ms.openlocfilehash: cd9a97f1b0d9c9eecfa6a42f735f21a42fd846e9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753236"
---
# <a name="compiler-error-c3717"></a>Compilerfehler C3717

' Methode ': eine Methode, die Ereignisse auslöst, kann nicht definiert werden.

Sie haben eine Ereignismethode deklariert, die eine-Implementierung enthält. Eine [__event](../../cpp/event.md) Methoden Deklaration darf keine Definition aufweisen. Stellen Sie sicher, dass keine Deklarationen der Ereignismethode Definitionen aufweisen, um diesen Fehler zu beheben. Entfernen Sie z. b. im folgenden Code den Funktions Text aus der `event1` Deklaration, wie in den Kommentaren angegeben.

Im folgenden Beispiel wird C3717 generiert:

```cpp
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
