---
title: "Compilerwarnung (Stufe 1) C4085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4085"
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerwarnung (Stufe 1) C4085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pragma\-Parameter "on" oder "off" erwartet  
  
 Das Pragma erfordert einen **on**\- oder **off**\-Parameter. Das Pragma wird ignoriert.  
  
 Im folgenden Beispiel wird C4085 generiert:  
  
```  
// C4085.cpp // compile with: /W1 /LD #pragma optimize( "t", maybe )  // C4085  
```