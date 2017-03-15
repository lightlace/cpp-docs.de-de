---
title: "__wbinvd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__wbinvd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wbinvd (systemintern)"
  - "wbinvd-Anweisung"
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __wbinvd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die Anweisung ungültig erklärt und schreibens\-Rückseite des Caches \(`wbinvd`\).  
  
## Syntax  
  
```  
void __wbinvd(void);  
```  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__wbinvd`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Funktion befindet sich im Kernelmodus mit einem Berechtigungsebene \(0\) KOMPLETT nur verfügbar, und die Routine als systeminterne Funktion ist nur verfügbar.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)