---
title: "__readeflags | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readeflags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readeflags intrinsic"
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __readeflags
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Liest das Programmstatus\- und \-steuer\(EFLAGS\) Register.  
  
## Syntax  
  
```  
unsigned     int __readeflags(void);  
unsigned __int64 __readeflags(void);  
```  
  
## Rückgabewert  
 Der Wert des EFLAGS\-Registers.  Der Rückgabewert ist 32 Bits lang auf einer 32\-Bit\-Plattform und 64 Bits lang auf einer 64\-Bit\-Plattform.  
  
## Hinweise  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__readeflags`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_writeeflags](../intrinsics/writeeflags.md)