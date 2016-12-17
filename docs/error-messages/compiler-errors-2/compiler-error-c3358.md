---
title: "Compilerfehler C3358"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3358"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3358"
ms.assetid: 180b93df-e78f-441a-91fb-1594c681f7f0
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3358
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Symbol": Symbol konnte nicht gefunden werden  
  
 Das geforderte Symbol wurde nicht gefunden.  
  
 Im folgenden Beispiel wird C3358 generiert:  
  
```  
// C3358.cpp #define __ATLEVENT_H__ 1   // remove this line to resolve the error #define _ATL_ATTRIBUTES 1 #include "atlbase.h" #include "atlcom.h" [event_receiver(com)] struct A   // C3358 { void func(); }; int main() { }  
```