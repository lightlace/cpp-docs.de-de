---
title: "__incfsbyte, __incfsword, __incfsdword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__incfsword"
  - "__incfsbyte_cpp"
  - "__incfsbyte"
  - "__incfsdword"
  - "__incfsword_cpp"
  - "__incfsdword_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__incfsword (systemintern)"
  - "__incfsdword (systemintern)"
  - "__incfsbyte (systemintern)"
ms.assetid: 820457fb-e35e-42d3-bcb6-725da3281c64
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# __incfsbyte, __incfsword, __incfsdword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Fügen Sie einen Wert hinzu, die an einer bestimmten Speicheradresse durch einen Offset relativ zum Anfang des Abschnitts `FS` angegeben wird.  
  
## Syntax  
  
```  
void __incfsbyte(   
   unsigned long Offset   
);  
void __incfsword(   
   unsigned long Offset   
);  
void __incfsdword(   
   unsigned long Offset  
);  
```  
  
#### Parameter  
 \[in\] `Offset`  
 Der Offset vom Anfang `FS`.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__incfsbyte`|x86|  
|`__incfsword`|x86|  
|`__incfsdword`|x86|  
  
## Hinweise  
 Diese systeminternen Komponenten sind im Kernelmodus nur verfügbar, und die Routinen sind als systeminterne Funktionen nur verfügbar.  
  
## BEENDEN Sie Microsoft\-Besonderen  
  
## Siehe auch  
 [\_\_addfsbyte, \_\_addfsword, \_\_addfsdword](../intrinsics/addfsbyte-addfsword-addfsdword.md)   
 [\_\_readfsbyte, \_\_readfsdword, \_\_readfsqword, \_\_readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [\_\_writefsbyte, \_\_writefsdword, \_\_writefsqword, \_\_writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)