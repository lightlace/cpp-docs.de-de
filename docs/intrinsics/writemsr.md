---
title: "__writemsr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__writemsr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Write Model Specific Register-Anweisung"
  - "wrmsr-Anweisung"
  - "__writemsr intrinsic"
ms.assetid: 938b1553-51a8-4822-a818-6bed79b0fde5
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __writemsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert das Modell der Schreibvorgang bestimmte Anweisung des Registers \(`wrmsr`\).  
  
## Syntax  
  
```  
void __writemsr(   
   unsigned long Register,   
   unsigned __int64 Value   
);  
```  
  
#### Parameter  
 \[in\] `Register`  
 Das Modell spezielle Register.  
  
 \[in\] `Value`  
 Der zu schreibende Wert.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__writemsr`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Funktion kann nur im Kernelmodus verwendet werden, und diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)