---
title: "__indword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__indword_cpp"
  - "__indword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "in-Anweisung"
  - "__indword intrinsic"
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __indword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Liest ein Doppelwort der Daten aus dem angegebenen Port mit der `in`\-Anweisung.  
  
## Syntax  
  
```  
unsigned long __indword(  
   unsigned short Port  
);  
```  
  
#### Parameter  
 \[in\] `Port`  
 Der zum Lesen von Port.  
  
## Rückgabewert  
 Das Wort Port aus dem gelesen werden soll.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__indword`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)