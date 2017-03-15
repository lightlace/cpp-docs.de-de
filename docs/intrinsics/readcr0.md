---
title: "__readcr0 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readcr0"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readcr0 intrinsic"
ms.assetid: 25bdb093-d83c-48d7-9c0f-224de8e2c61c
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __readcr0
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Liest das CR0\-Register und gibt dessen Wert zurück.  
  
## Syntax  
  
```  
unsigned long __readcr0(void);  /* X86 */ unsigned __int64 __readcr0(void);  /* X64 */   
```  
  
## Rückgabewert  
 Der Wert im CR0\-Register.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`__readcr0`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese systeminterne Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)