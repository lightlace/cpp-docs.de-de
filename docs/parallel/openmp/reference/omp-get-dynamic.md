---
title: "omp_get_dynamic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_get_dynamic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_dynamic OpenMP function"
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# omp_get_dynamic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Wert zurück, der angibt, ob die Anzahl der Threads, die im Folgenden parallelen Bereich verfügbar sind, von der Laufzeit angepasst werden kann.  
  
## Syntax  
  
```  
int omp_get_dynamic();  
```  
  
## Rückgabewert  
 Wenn ungleich 0 \(null\), dynamische Anpassung von Threads aktiviert ist.  
  
## Hinweise  
 Dynamische Anpassung von Threads wird mit [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) und [OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)angegeben.  
  
 Weitere Informationen finden Sie unter [3.1.7 omp\_set\_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) als ein Beispiel für die Verwendung von `omp_get_dynamic`.  
  
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)