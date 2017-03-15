---
title: "__readcr3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readcr3"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readcr3 intrinsic"
ms.assetid: e24392c3-cad7-4788-8f31-94bf2e9e0053
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __readcr3
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Liest das CR3\- Register und gibt den Wert zurück.  
  
## Syntax  
  
```  
unsigned __int64 __readcr3(void);  
```  
  
## Rückgabewert  
 Der Wert im CR3\-Register.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__readcr3`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese systeminternen im Kernelmodus ist nur verfügbar, und die Routine als systeminterne Funktion ist nur verfügbar.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)