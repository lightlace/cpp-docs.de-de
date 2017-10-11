---
title: Compilerfehler C3714 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3714
dev_langs:
- C++
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7d58e06d99975fd4ccff9ea4bace755ff1d758cb
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3714"></a>Compilerfehler C3714
'Methode': eine Ereignishandlermethode muss die gleiche Aufrufkonvention als Quelle für 'Methode' haben  
  
 Sie definiert eine Ereignishandlermethode, die nicht die gleiche Aufrufkonvention als die Quellereignismethode verwendet haben. Um diesen Fehler zu beheben, geben Sie der Ereignishandlermethode die gleichen Aufrufkonventionen als die von der Quellereignismethode. Stellen Sie z. B. in den folgenden Code die Aufrufkonventionen von `handler1` und `event1` entsprechen ([__cdecl](../../cpp/cdecl.md) oder [__stdcall](../../cpp/stdcall.md) oder andere). Entfernen von Aufrufen von Konvention Schlüsselwörter aus beiden Deklarationen ebenfalls dieses Problem beheben, und dazu führen, dass `event1` und `handler1` standardmäßig ist die [Thiscall](../../cpp/thiscall.md) Aufrufkonvention. Finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md) für Weitere Informationen.  
  
 Im folgende Beispiel wird C3714 generiert:  
  
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
