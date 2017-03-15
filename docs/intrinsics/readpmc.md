---
title: "__readpmc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readpmc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Read Performance Monitoring Counters-Anweisung"
  - "__readpmc intrinsic"
  - "rdpmc-Anweisung"
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __readpmc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die `rdpmc`\-Anweisung, die den Indikator Leistungsüberwachungs gelesen, der von `counter`angegeben wird.  
  
## Syntax  
  
```  
unsigned __int64 __readpmc(   
   unsigned long counter   
);  
```  
  
#### Parameter  
 \[in\] `counter`  
 Die Leistung Zähler gelesen werden soll.  
  
## Rückgabewert  
 Der Wert des angegebenen Leistungsindikators.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__readpmc`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das systeminterne ist nur im Kernelmodus verfügbar, und die Routine als systeminterne Funktion ist nur verfügbar.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)