---
title: "_disable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_disable_cpp"
  - "_disable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_disable intrinsic"
  - "disable intrinsic"
  - "rsm instruction"
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _disable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Deaktiviert Unterbrechungen.  
  
## Syntax  
  
```  
void _disable(void);  
```  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`_disable`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 `_disable` weist den Prozessor an, das Interrupt\-Flag zu deaktivieren.  Unter x86\-Systemen erzeugt diese Funktion die Anweisung für das Clear Interrupt Flag \(`cli`\).  
  
 Diese Funktion ist nur im Kernelmodus verfügbar.  Wenn sie im Benutzermodus verwendet wird, wird zur Laufzeit eine privilegierte Anweisungsausnahme ausgelöst.  
  
 Auf ARM\-Plattformen ist diese Routine nur als systeminterne Funktion verfügbar.  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)