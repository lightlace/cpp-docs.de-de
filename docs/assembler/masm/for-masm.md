---
title: "FOR (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "for"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FOR directive"
ms.assetid: 99872e61-f503-4d34-b305-59f8556ba6b7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# FOR (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Markiert einen Block, der einmal für jedes `argument`wiederholt wird, wenn die aktuelle `argument` bei jeder Wiederholung `parameter` ersetzt.  
  
## Syntax  
  
```  
  
   FOR   
   parameter [[:REQ | :=default]] , <argument [[, argument]]...>  
statements  
ENDM  
```  
  
## Hinweise  
 Identisch mit [IRP](../../assembler/masm/irp.md).  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)