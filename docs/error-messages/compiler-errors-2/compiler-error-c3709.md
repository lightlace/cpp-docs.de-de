---
title: "Compilerfehler C3709"
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
  - "C3709"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3709"
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3709
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Ungültige Syntax zur Bestimmung des Ereignisses in \_\_hook\/\_\_unhook  
  
 Wenn Sie eine Ereignisquelle mit [\_\_hook](../../cpp/hook.md) oder [\_\_unhook](../../cpp/unhook.md) angeben, muss der erste Parameter eine gültige Ereignismethode und der zweite Parameter ein gültiges Ereignisquellobjekt \(und keine Methode\) sein.  
  
 Im folgenden Beispiel wird C3709 generiert:  
  
```  
// C3709.cpp  
// compile with: /LD  
[event_source(native)]  
class CEventSrc  
{  
public:  
   __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec  
{  
public:  
   void handler1()  
   {  
   }  
  
   void HookEvents(CEventSrc* pSrc)  
   {  
      __hook(bad, pSrc, CEventRec::handler1);   // C3709  
      // Try the following line instead:  
      // __hook(&CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
  
   void UnhookEvents(CEventSrc* pSrc)  
   {  
      __unhook(&CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
};  
```