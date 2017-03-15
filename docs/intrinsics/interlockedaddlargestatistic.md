---
title: "_InterlockedAddLargeStatistic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedAddLargeStatistic"
  - "_InterlockedAddLargeStatistic_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedAddLargeStatistic intrinsic"
  - "InterlockedAddLargeStatistic intrinsic"
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _InterlockedAddLargeStatistic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Führt eine ineinandergegriffene Hinzufügung aus, in der der erste Operand ein 64\-Bit\-Wert ist.  
  
## Syntax  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### Parameter  
 \[in, out\]  `Addend`  
 Ein Zeiger auf den ersten Operanden der Operation Hinzufügen.  Der Wert, der angezeigt wird, wird durch das Ergebnis der Addition ersetzt.  
  
 \[in\] `Value`  
 Der zweite Operand. dem ersten Operanden hinzuzufügende Wert.  
  
## Rückgabewert  
 Der Wert des zweiten Operanden.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Dies ist keine systeminterne atomar, weil er als zwei einzelne gesperrte Anweisungen implementiert wird.  Ein unteilbares 64\-Bit gelesen, das in einem anderen Thread während der Ausführung der systeminternen konnte einen inkonsistenten Wert ergeben auftritt, der gelesen wird.  
  
 Diese Funktion verhält sich wie eine Lese\-\/Schreibeigenschaft barriere.  Weitere Informationen finden Sie unter [\_ReadWriteBarrier](../intrinsics/readwritebarrier.md).  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Konflikt mit dem x86\-Compiler](../build/conflicts-with-the-x86-compiler.md)