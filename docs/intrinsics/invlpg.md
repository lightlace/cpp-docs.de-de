---
title: "__invlpg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__invlpg"
  - "__invlpg_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invlpg-Anweisung"
  - "__invlpg intrinsic"
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __invlpg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die Anweisung x86s `invlpg` , die den Adressenumsetzpuffer \(TLB\) für die Seite ungültig macht, die dem Speicher belegt wird, die von der `Address`angezeigt wird.  
  
## Syntax  
  
```  
void __invlpg(  
   void* Address  
);  
```  
  
#### Parameter  
 \[in\]    `Address`  
 Eine 64\-Bit\-Adresse.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__invlpg`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Systeminterne `__invlpg` gibt eine privilegierte Anweisung aus und ist im Kernelmodus mit einem Berechtigungsebene \(0\) KOMPLETT nur verfügbar.  
  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)