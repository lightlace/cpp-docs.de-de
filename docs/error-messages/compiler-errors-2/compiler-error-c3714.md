---
title: "Compilerfehler C3714"
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
  - "C3714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3714"
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3714
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Methode': Eine Ereignishandlermethode muss dieselbe Aufrufkonvention wie die Quelle 'Methode' haben  
  
 Sie haben eine Ereignishandlermethode definiert, die nicht dieselbe Aufrufkonvention verwendet wie die Quellereignismethode.  Um diesen Fehler zu beheben, weisen Sie der Ereignishandlermethode dieselben Aufrufkonventionen wie der Quellereignismethode zu.  Im folgenden Code passen Sie z. B. die Aufrufkonventionen von `handler1` und `event1` \([\_\_cdecl](../../cpp/cdecl.md) oder [\_\_stdcall](../../cpp/stdcall.md) bzw. andere\) an.  Außerdem können Sie das Problem beheben, indem Sie die Schlüsselwörter für die Aufrufkonventionen aus beiden Deklarationen entfernen, sodass `event1` und `handler1` standardmäßig die Aufrufkonvention [thiscall](../../cpp/thiscall.md) verwenden.  Weitere Informationen finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md).  
  
 Im folgenden Beispiel wird C3714 generiert:  
  
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