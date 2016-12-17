---
title: "firstprivate"
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
  - "firstprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "firstprivate OpenMP clause"
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# firstprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass jeder Thread seine eigene Instanz einer Variablen zugewiesen werden soll, und dass die Variable mit dem Wert der Variable initialisiert werden soll, da sie vor dem parallelen Konstrukt vorhanden ist.  
  
## Syntax  
  
```  
firstprivate(var)  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`var`|Die Variable, wenn Instanzen in jedem Thread und dem wird mit dem Wert der Variable initialisiert, da sie vor dem parallelen Konstrukt vorhanden ist.  Wenn mehrere Variablen angegeben wird, separate Variablennamen durch Kommas.|  
  
## Hinweise  
  
## Hinweise  
 `firstprivate` gilt für die folgenden Direktiven an:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).  
  
## Beispiel  
 Ein Beispiel für die Verwendung von `firstprivate`finden Sie im Beispiel in [private](../../../parallel/openmp/reference/private-openmp.md).  
  
## Siehe auch  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)