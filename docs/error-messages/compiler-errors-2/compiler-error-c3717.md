---
title: "Compilerfehler C3717 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3717"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3717"
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3717
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Methode': Eine Methode, die Ereignisse auslöst, kann nicht definiert werden  
  
 Sie haben eine Ereignismethode deklariert, die eine Implementierung einschließt.  Die Deklaration einer [\_\_event](../../cpp/event.md)\-Methode kann keine Definition enthalten.  Um diesen Fehler zu beheben, sollten Sie sicherstellen, dass keine Ereignismethodendeklaration über Definitionen verfügt.  Entfernen Sie im folgenden Code beispielsweise den Funktionstext aus der Deklaration `event1`. Siehe entsprechende Kommentare.  
  
 Im folgenden Beispiel wird C3717 generiert:  
  
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