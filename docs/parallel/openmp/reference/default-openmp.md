---
title: "default (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default OpenMP clause"
  - "defaults, OpenMP clause"
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# default (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt das Verhalten von unscoped Variablen in einem parallelen Bereich an.  
  
## Syntax  
  
```  
default(shared | none)  
```  
  
## Hinweise  
 `shared`, die aktiv ist, wenn die `default`\-Klausel nicht angegeben wird, hat zur Folge, dass jede Variable in einem parallelen Bereich behandelt wird, als ob sie mit der [shared](../../../parallel/openmp/reference/shared-openmp.md)\-Klausel angegeben wurde.  `none` bedeutet, dass alle Variablen, die in einem parallelen Bereich verwendet werden, die nicht mit [private](../../../parallel/openmp/reference/private-openmp.md)ausgewertet werden, in [shared](../../../parallel/openmp/reference/shared-openmp.md), in [reduction](../../../parallel/openmp/reference/reduction.md), in [firstprivate](../../../parallel/openmp/reference/firstprivate.md)oder [lastprivate](../../../parallel/openmp/reference/lastprivate.md)\-Klausel ein Compilerfehler verursacht.  
  
 `default` gilt für die folgenden Direktiven an:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.5 default](../../../parallel/openmp/2-7-2-5-default.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [private](../../../parallel/openmp/reference/private-openmp.md) als ein Beispiel für die Verwendung von `default`.  
  
## Siehe auch  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)