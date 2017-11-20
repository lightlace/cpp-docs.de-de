---
title: "__readmsr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readmsr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Read Model Specific Register"
  - "rdmsr-Anweisung"
  - "__readmsr (systemintern)"
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __readmsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die `rdmsr`\-Anweisung, die die modellspezifische Register liest, das von `register` angegeben ist und dessen Wert zurückgibt.  
  
## Syntax  
  
```  
__int64 __readmsr(   
   int register   
);  
```  
  
#### Parameter  
 \[in\] `register`  
 Das zu lesende Register bestimmte des Modells.  
  
## Rückgabewert  
 Der Wert im angegebenen Register.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__readmsr`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Funktion ist nur im Kernelmodus verfügbar, und die Routine als systeminterne Funktion ist nur verfügbar.  
  
 Weitere Informationen finden Sie in der AMD\-Dokumentation.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)