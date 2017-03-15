---
title: "__halt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__halt"
  - "__halt_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__halt (systemintern)"
  - "HLT-Anweisung"
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __halt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Enthält den Mikroprozessor an, bis eine aktivierte Unterbrechen, eine nicht maskierbare Umbruch \(Reset\) oder eine NMI auftritt.  
  
## Syntax  
  
```  
void __halt( void );  
```  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__halt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Die `__halt`\-Funktion ähnelt dem `HLT` Computeranweisung, und ist nur im Kernelmodus verfügbar.  Weitere Informationen Suche nach dem Dokument, das Handbuch „des Intel\-Architektur\-Softwareentwicklers, Volume 2: Anweisungs\-festgelegter Verweis“ auf der Website [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) .  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)