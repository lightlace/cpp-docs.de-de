---
title: Compilerfehler C3714
ms.date: 11/04/2016
f1_keywords:
- C3714
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
ms.openlocfilehash: 1078bf8a97f6cb7afeaf7046489fe262c0bb0199
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753327"
---
# <a name="compiler-error-c3714"></a>Compilerfehler C3714

"Methode": eine Ereignishandlermethode muss dieselbe Aufruf Konvention wie die Quelle "Method" aufweisen.

Sie haben eine Ereignishandlermethode definiert, die nicht dieselbe Aufruf Konvention wie die Quell Ereignismethode verwendet hat. Um diesen Fehler zu beheben, müssen Sie der Ereignishandlermethode dieselben Aufruf Konventionen wie die der Quell Ereignismethode übergeben. Nehmen Sie z. b. im folgenden Code die Aufruf Konventionen `handler1` und `event1` Übereinstimmungen ([__cdecl](../../cpp/cdecl.md) oder [__stdcall](../../cpp/stdcall.md) oder andere). Das Entfernen von Schlüsselwörtern für die Aufruf Konvention aus beiden Deklarationen löst auch das Problem und bewirkt, dass `event1` und `handler1` standardmäßig die Aufruf Konvention " [Thiscall](../../cpp/thiscall.md) " haben. Weitere Informationen finden Sie unter [Aufrufen von Konventionen](../../cpp/calling-conventions.md) .

Im folgenden Beispiel wird C3714 generiert:

```cpp
// C3714.cpp
// compile with: /c
// processor: x86
[event_source(native)]
class CEventSrc {
public:
   __event void __cdecl event1();
   // try the following line instead
   // __event void __stdcall event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void __stdcall handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714
   }

   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714
   }
};
```
