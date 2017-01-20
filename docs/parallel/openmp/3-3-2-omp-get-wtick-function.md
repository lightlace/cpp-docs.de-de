---
title: "3.3.2 omp_get_wtick Function"
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
ms.assetid: 1ad08500-bcb0-40d9-a81f-f131819006c9
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# 3.3.2 omp_get_wtick Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `omp_get_wtick`\-Funktion gibt einen Gleitkommawert mit doppelter Genauigkeit gleich der Anzahl der Sekunden zwischen aufeinander folgender Teilstrichen zurück.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
double omp_get_wtick(void);  
```