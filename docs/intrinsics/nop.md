---
title: "__nop | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__nop"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nop-Anweisung"
  - "__nop, (systemintern)"
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __nop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert plattformspezifische Computercode, der keinen Vorgang ausführt.  
  
## Syntax  
  
```  
void __nop();  
```  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__nop`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## BEENDEN Sie Microsoft\-Besonderen  
  
## Hinweise  
 Die `__nop`\-Funktion ähnelt dem `NOP` Computeranweisung.  Weitere Informationen finden Sie unter „das Dokument für die Führungslinie des Intel\-Architektur\-Softwareentwicklers, Volume 2: Anweisungs\-festgelegter Verweis“ auf der Website [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) .  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_noop](../intrinsics/noop.md)