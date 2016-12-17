---
title: "barrier"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "barrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "barrier OpenMP directive"
ms.assetid: 5c73ad4f-c768-443a-8f9e-4fd8bc2253c7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# barrier
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Synchronisiert alle Threads in einem Team; Alle Thread pause an der Grenze, bis alle Threads die Barriere ausführen.  
  
## Syntax  
  
```  
#pragma omp barrier  
```  
  
## Hinweise  
 Die `barrier`\-Direktiven unterstützen keine OpenMP\-Klauseln.  
  
 Weitere Informationen finden Sie unter [2.6.3 barrier Directive](../../../parallel/openmp/2-6-3-barrier-directive.md).  
  
## Beispiel  
 Ein Beispiel dafür, wie `barrier`finden Sie unter [master](../../../parallel/openmp/reference/master.md)verwendet.  
  
## Siehe auch  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)