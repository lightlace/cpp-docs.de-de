---
title: Compilerfehler C3714 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3714
dev_langs:
- C++
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7102378acc2fe12335f1f2b3579f93cf02161b16
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109651"
---
# <a name="compiler-error-c3714"></a>Compilerfehler C3714

"Method": eine Ereignishandlermethode muss dieselbe Aufrufkonvention wie die Quelle 'Methode' haben

Sie definiert eine Ereignishandlermethode, die nicht dieselbe Aufrufkonvention wie die Quelle Ereignis-Methode verwendet haben. Um diesen Fehler zu beheben, geben Sie der Ereignishandlermethode die Konventionen für die gleichen aufrufen wie die Quell-Methode. Stellen Sie z. B. in den folgenden Code, die Aufrufkonventionen der `handler1` und `event1` entsprechen ([__cdecl](../../cpp/cdecl.md) oder [__stdcall](../../cpp/stdcall.md) oder andere). Entfernen von Aufrufen Konvention Schlüsselwörter aus beiden Deklarationen wird auch das Problem lösen, und dazu führen, dass `event1` und `handler1` standardmäßig ist die [Thiscall](../../cpp/thiscall.md) Aufrufkonvention. Finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md) für Weitere Informationen.

Im folgende Beispiel wird die C3714 generiert:

```
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