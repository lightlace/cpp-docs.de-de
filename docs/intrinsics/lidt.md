---
title: "__lidt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__lidt"
  - "__lidt_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIDT-Anweisung"
  - "__lidt (systemintern)"
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __lidt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Lädt das Unterbrechen deskriptor\-Tabellen register \(IDTR\) mit dem Wert an der angegebenen Speicheradresse.  
  
## Syntax  
  
```  
void __lidt(  
     void *Source);  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|\[in\] `Source`|Zeiger auf dem IDTR zu kopierende Wert.|  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__lidt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Die `__lidt`\-Funktion ähnelt dem `LIDT` Computeranweisung, und ist nur im Kernelmodus verfügbar.  Weitere Informationen Suche nach dem Dokument, das Handbuch „des Intel\-Architektur\-Softwareentwicklers, Volume 2: Anweisungs\-festgelegter Verweis“ auf der Website [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) .  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_sidt](../intrinsics/sidt.md)