---
title: "Compilerwarnung (Stufe 1) C4997"
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
  - "C4997"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4997"
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4997
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„class“: Die Co\-Klasse implementiert keine COM\- oder Pseudoschnittstelle.  
  
 Eine mit dem [coclass](../../windows/coclass.md)\-Attribut markierte Klasse hat keine Schnittstelle implementiert.  
  
 Im folgenden Beispiel wird C4997 generiert.  
  
```  
// C4997.cpp // compile with: /WX // to resolve this C4997, uncomment all code #include <objbase.h> [ object ] __interface I { HRESULT func(); }; [ coclass ] struct C /*: I*/ { /* HRESULT func() { return S_OK; } */ };   // C4997  
```