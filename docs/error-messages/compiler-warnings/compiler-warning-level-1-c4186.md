---
title: "Compilerwarnung (Stufe 1) C4186 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4186"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4186"
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4186
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import\-Attribut "Attribut" erfordert Anzahl Argumente; ignoriert  
  
 Ein `#import`\-Attribut weist die falsche Anzahl von Argumenten auf.  
  
## Beispiel  
  
```  
// C4186.cpp // compile with: /W1 /c #import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186  
```  
  
 Das `no_namespace`\-Attribut akzeptiert keine Argumente. Das **rename**\-Attribut erhält nur zwei Argumente.