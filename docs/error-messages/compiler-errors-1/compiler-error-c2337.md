---
title: "Compilerfehler C2337"
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
  - "C2337"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2337"
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2337
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Attributname': Das Attribut wurde nicht gefunden.  
  
 Sie haben ein Attribut verwendet, das in dieser Version von Visual C\+\+ nicht unterstützt wird.  
  
 Im folgenden Beispiel wird C2337 generiert:  
  
```  
// C2337.cpp // compile with: /c [emitidl]; [module(name="x")]; [grasshopper]   // C2337, not a supported attribute class a{};  
```