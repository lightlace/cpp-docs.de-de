---
title: "Compilerfehler C3743 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3743"
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Hook\/unhook kann nur auf eine gesamte Schnittstelle angewendet werden, wenn der "layout\_dependent"\-Parameter von event\_receiver True ist  
  
 Die [\_\_unhook](../../cpp/unhook.md)\-Funktion variiert hinsichtlich der Anzahl der Parameter, die sie je nach dem Wert, der an den `layout_dependent`\-Parameter in der [event\_receiver](../../windows/event-receiver.md)\-Klasse übergeben wurde, aufnehmen kann.  
  
 Im folgenden Beispiel wird C3743 generiert:  
  
```  
// C3743.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
[object] __interface I { HRESULT f(); };  
  
[event_receiver(com, layout_dependent=true), coclass]  
struct R : I {  
        HRESULT f() {  
      return 0;  
   }  
        R() {  
   }  
  
   R(I* a) {  
      __hook(I, a, &R::f);   // C3743  
      // The following line resolves the error.  
      // __hook(I, a);  
   }  
};  
```