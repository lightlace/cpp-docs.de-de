---
title: "__readfsbyte, __readfsdword, __readfsqword, __readfsword"
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
  - "__readfsword"
  - "__readfsdword"
  - "__readfsbyte"
  - "__readfsqword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readfsword intrinsic"
  - "readfsword intrinsic"
  - "__readfsdword intrinsic"
  - "readfsbyte intrinsic"
  - "__readfsbyte intrinsic"
  - "readfsdword intrinsic"
  - "readfsqword intrinsic"
  - "__readfsqword intrinsic"
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# __readfsbyte, __readfsdword, __readfsqword, __readfsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Lesen von Arbeitsspeicher von einem Speicherort, auf den ein Offset relativ zum Anfang des FS segments angegeben wurde.  
  
## Syntax  
  
```  
unsigned char __readfsbyte(   
   unsigned long Offset   
);  
unsigned short __readfsword(   
   unsigned long Offset   
);  
unsigned long __readfsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readfsqword(   
   unsigned long Offset   
);  
```  
  
#### Parameter  
 \[in\] `Offset`  
 Der Offset vom Anfang `FS` zum Lesen aus.  
  
## Rückgabewert  
 Der Inhalt des Bytes Speicherplatz des Worts oder des Quadword des Doppelworts \(z. B. mit dem Namen die angegebene Funktion aufgerufen\) am Speicherort `FS:[``Offset``]`.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__readfsbyte`|x86|  
|`__readfsdword`|x86|  
|`__readfsqword`|x86|  
|`__readfsword`|x86|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [\_\_writefsbyte, \_\_writefsdword, \_\_writefsqword, \_\_writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)