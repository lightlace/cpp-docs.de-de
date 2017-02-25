---
title: "OMP_SCHEDULE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OMP_SCHEDULE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_SCHEDULE OpenMP environment variable"
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# OMP_SCHEDULE
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ändert das Verhalten der [schedule](../../../parallel/openmp/reference/schedule.md)\-Klausel, wenn `schedule(runtime)` in `for` oder `parallel for`\-Direktive angegeben wird.  
  
## Syntax  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `size` \(optional\)  
 Gibt die Größe der Iterationen an.  `size` muss eine positive ganze Zahl sein.  Der Standardwert ist 1, außer wenn `type` statisch ist.  Nicht zulässig, wenn `type``runtime`ist.  
  
 `type`  
 Die Art der Planung:  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## Hinweise  
 Der Standardwert in der Visual C\+\+\-Implementierung des OpenMP\-Standards ist `OMP_SCHEDULE=static,0`.  
  
 Weitere Informationen finden Sie unter [4.1 OMP\_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).  
  
## Beispiel  
 Mit dem folgenden Befehl wird die **OMP\_SCHEDULE** Umgebungsvariable fest:  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 Der folgende Befehl zeigt die aktuelle Einstellung der **OMP\_SCHEDULE** Umgebungsvariablen an:  
  
```  
set OMP_SCHEDULE  
```  
  
## Siehe auch  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)