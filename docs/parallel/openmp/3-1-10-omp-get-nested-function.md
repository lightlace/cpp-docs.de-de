---
title: "3.1.10 omp_get_nested Function"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.10 omp_get_nested Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `omp_get_nested`\-Funktion gibt einen Wert ungleich 0 \(null\) zurück, wenn geschachtelter Parallelität und 0 aktiviert wird, wenn er deaktiviert ist.  Weitere Informationen zu geschachtelten Parallelität finden Sie in Abschnitt 3.1.9 auf Seite 40.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 Wenn eine Implementierung nicht geschachtelten Parallelität implementiert, gibt diese Funktion immer 0 zurück.