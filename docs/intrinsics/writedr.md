---
title: "__writedr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__writedr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__writedr intrinsic"
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __writedr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schreibt den angegebenen Wert für das angegebene Register debuggen.  
  
## Syntax  
  
```  
void __writedr(unsigned DebugRegister, unsigned DebugValue);  
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue);  
```  
  
#### Parameter  
 \[in\] `DebugRegister`  
 Eine Zahl von 0 bis 7, die das Debuggen Register angibt.  
  
 \[in\]`DebugValue`  
 Ein Register Debuggen auf das zu schreibende Wert.  
  
## Hinweise  
 Diese systeminternen Komponenten sind nur im Kernelmodus verfügbar, und die Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__writedr`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_readdr](../intrinsics/readdr.md)