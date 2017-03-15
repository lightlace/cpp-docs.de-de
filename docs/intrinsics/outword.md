---
title: "__outword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__outword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__outword intrinsic"
  - "out-Anweisung"
ms.assetid: 995f8834-0f50-4b4f-a7a2-af0e7c371cda
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __outword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die `out`\-Anweisung, die das Wort `Data` der E\/A\-Port bereitgestellt wird, der von `Port`angegeben wird.  
  
## Syntax  
  
```  
void __outword(   
   unsigned short Port,   
   unsigned short Data   
);  
```  
  
#### Parameter  
 \[in\] `Port`  
 Der Anschluss, um die Daten zu senden.  
  
 \[in\] `Data`  
 Die zu sendenden Daten.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__outword`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)