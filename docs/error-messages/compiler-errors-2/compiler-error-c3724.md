---
title: "Compilerfehler C3724 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3724"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3724"
ms.assetid: cab8aba7-14fc-406f-8cc6-32744c8f31c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3724
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#include \<windows.h,\> um Multithreading mit Ereignissen zu verwenden  
  
 Zur Verwendung von Multithreading mit Ereignissen ist die Datei **windows.h** erforderlich.  Um diesen Fehler zu beheben, fügen Sie `#include <windows.h>` am Anfang der Datei ein, in der Ereignisquellen und Ereignisempfänger definiert sind.  
  
```  
// C3724.cpp  
// uncomment the following line to resolve  
// #include <windows.h>  
  
[event_source(native), threading(apartment)]  
class CEventSrc {  
public:  
   __event void event1();   // C3724  
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