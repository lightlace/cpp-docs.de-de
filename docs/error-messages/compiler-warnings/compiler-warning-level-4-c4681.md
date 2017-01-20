---
title: "Compilerwarnung (Stufe 4) C4681"
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
  - "C4681"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4681"
ms.assetid: a4e6d85f-3e21-4b45-a551-c23d3c554d3f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4681
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„class“: Die Co\-Klasse gibt keine Standardschnittstelle an, die eine Ereignisquelle ist.  
  
 Eine [source](../../windows/source-cpp.md)\-Schnittstelle wurde für eine Klasse nicht angegeben.  
  
 Im folgenden Beispiel wird C4681 generiert:  
  
```  
// C4681.cpp // compile with: /W4 /c #define _ATL_ATTRIBUTES 1 #include <atlbase.h> #include <atlcom.h> [module(name="test")]; [dual, uuid("00000000-0000-0000-0000-000000000000")] __interface IEvent { [id(3)] HRESULT myEvent(); }; [object, uuid("00000000-0000-0000-0000-000000000001")] __interface ISource { HRESULT Fire(); }; [ coclass, source(IEvent), default(ISource), // Uncomment the following line to resolve. // default(IEvent), uuid("00000000-0000-0000-0000-000000000002") ] struct CSource : ISource {   // C4681 HRESULT Fire() { return 0; } };  
```