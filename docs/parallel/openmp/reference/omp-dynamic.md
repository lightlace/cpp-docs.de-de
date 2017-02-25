---
title: "OMP_DYNAMIC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OMP_DYNAMIC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_DYNAMIC OpenMP environment variable"
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# OMP_DYNAMIC
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob die OpenMP\-Laufzeit die Anzahl von Threads in einem parallelen Bereichs angepasst werden kann.  
  
## Syntax  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## Hinweise  
 Die `OMP_DYNAMIC` Umgebungsvariable kann über die [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)\-Funktion überschrieben werden.  
  
 Der Standardwert in der Visual C\+\+\-Implementierung des OpenMP\-Standards ist `OMP_DYNAMIC=FALSE`.  
  
 Weitere Informationen finden Sie unter [4.3 OMP\_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).  
  
## Beispiel  
 Mit dem folgenden Befehl wird die `OMP_DYNAMIC` Umgebungsvariable fest, um AUSZURICHTEN:  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 Der folgende Befehl zeigt die aktuelle Einstellung der `OMP_DYNAMIC` Umgebungsvariablen an:  
  
```  
set OMP_DYNAMIC  
```  
  
## Siehe auch  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)