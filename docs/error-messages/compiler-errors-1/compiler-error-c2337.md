---
title: "Compilerfehler C2337 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2337"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2337"
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2337
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Attributname': Das Attribut wurde nicht gefunden.  
  
 Sie haben ein Attribut verwendet, das in dieser Version von Visual C\+\+ nicht unterstützt wird.  
  
 Im folgenden Beispiel wird C2337 generiert:  
  
```  
// C2337.cpp // compile with: /c [emitidl]; [module(name="x")]; [grasshopper]   // C2337, not a supported attribute class a{};  
```