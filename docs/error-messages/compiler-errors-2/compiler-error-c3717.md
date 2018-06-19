---
title: Compilerfehler C3717 | Microsoft Docs
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
ms.openlocfilehash: efe6cdb53b3ee78016c25b273eb4682ec380d12f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264011"
---
# <a name="compiler-error-c3717"></a>Compilerfehler C3717
'Methode': eine Methode, die Ereignisse auslöst, kann nicht definiert werden  
  
 Sie deklariert eine Ereignismethode, die eine Implementierung enthält. Ein [__event](../../cpp/event.md) Methodendeklaration kann keine Definition aufweisen. Um diesen Fehler zu beheben, stellen Sie sicher, dass kein Ereignis Methodendeklarationen Definitionen aufweisen. Entfernen Sie z. B. in den folgenden Code den Hauptteil der Funktion aus der `event1` Deklaration wie durch die Kommentare angezeigt.  
  
 Im folgende Beispiel wird C3717 generiert:  
  
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