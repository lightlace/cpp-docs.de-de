---
title: "Compilerwarnung (Stufe 1) C4186"
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
  - "C4186"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4186"
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
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