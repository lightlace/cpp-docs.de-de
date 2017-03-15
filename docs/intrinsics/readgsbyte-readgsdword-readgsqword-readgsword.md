---
title: "__readgsbyte, __readgsdword, __readgsqword, __readgsword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readgsbyte"
  - "__readgsdword"
  - "__readgsqword"
  - "__readgsword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readgsword intrinsic"
  - "__readgsdword intrinsic"
  - "__readgsqword intrinsic"
  - "__readgsbyte intrinsic"
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# __readgsbyte, __readgsdword, __readgsqword, __readgsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Lesen von Arbeitsspeicher von einem Speicherort, auf den ein Offset relativ zum Anfang des GS\-Segments angegeben wurde.  
  
## Syntax  
  
```  
unsigned char __readgsbyte(   
   unsigned long Offset   
);  
unsigned short __readgsword(   
   unsigned long Offset   
);  
unsigned long __readgsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readgsqword(   
   unsigned long Offset   
);  
```  
  
#### Parameter  
 \[in\] `Offset`  
 Der Offset vom Anfang `GS` zum Lesen aus.  
  
## Rückgabewert  
 Der Inhalt des Bytes Speicherplatz des Worts oder des Quadword des Doppelworts \(z. B. mit dem Namen die angegebene Funktion aufgerufen\) am Speicherort `GS:[``Offset``]`.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__readgsbyte`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__readgsdword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__readgsqword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__readgsword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese systeminternen Komponenten sind im Kernelmodus nur verfügbar, und die Routinen sind als systeminterne Funktionen nur verfügbar.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [\_\_writegsbyte, \_\_writegsdword, \_\_writegsqword, \_\_writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)