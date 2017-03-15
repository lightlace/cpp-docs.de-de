---
title: "3.1.5 omp_get_num_procs Function"
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
ms.assetid: bbfbf17b-0c68-4ba6-a25d-07c36ecb551f
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.5 omp_get_num_procs Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `omp_get_num_procs`\-Funktion gibt die Anzahl der Prozessoren zurück, die auf das Programm zur Verfügung stehen, zu der Zeit, die die Funktion aufgerufen wird.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_num_procs(void);  
```