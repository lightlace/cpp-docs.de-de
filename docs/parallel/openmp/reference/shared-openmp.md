---
title: "shared (OpenMP)"
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
  - "Shared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shared OpenMP clause"
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# shared (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass eine oder mehrere Variablen mit allen Threads freigegeben werden sollen.  
  
## Syntax  
  
```  
shared(var)  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `var`  
 Ein mehr Freigeben von Variablen.  Wenn mehrere Variablen angegeben wird, separate Variablennamen durch Kommas.  
  
## Hinweise  
 Eine andere Möglichkeit, Variablen mit Threads freizugeben ist mit der copyprivat\-Klausel.  
  
 `shared` gilt für die folgenden Direktiven an:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.4 shared](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [private](../../../parallel/openmp/reference/private-openmp.md) als ein Beispiel für die Verwendung von `shared`.  
  
## Siehe auch  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)