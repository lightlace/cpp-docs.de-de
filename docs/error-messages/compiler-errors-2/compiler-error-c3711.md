---
title: "Compilerfehler C3711"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3711"
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Methode': Eine nicht verwaltete Ereignisquellmethode muss eine leere Rückgabe oder einen ganzzahligen Typ haben  
  
 Sie haben in der Ereignisquelle eine Methode definiert, durch die weder `void` noch ein ganzzahliger Typ zurückgegeben wurde.  Um diesen Fehler zu beheben, definieren Sie Ereignis und Ereignishandler so, dass diese den Rückgabetyp `void` oder einen ganzzahligen Typ wie `int` oder `long` haben.  
  
 Im folgenden Beispiel wird C3711 generiert:  
  
```  
// C3711.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[event_source(native)]  
class CEventSrc {  
public:  
   __event float event1();   // C3711  
   // try the following line instead  
   // __event int event1();  
   // also change the handler, below  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   float handler1() {         // change float to int  
      return 0.0;             // change 0.0 to 0  
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