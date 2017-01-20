---
title: "XMMWORD"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "XMMWORD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XMMWORD directive"
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# XMMWORD
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird für Multimedia Operanden des 128\-Bits mit MMX und XTM \(SSE\) \- Anweisungen.  
  
## Syntax  
  
```  
XMMWORD  
```  
  
## Hinweise  
 `XMMWORD` muss den gleichen Typ wie [\_\_m128](../../cpp/m128.md)darzustellen.  
  
## Beispiel  
  
```  
movdqa   xmm0, xmmword ptr [ebx]  
```