---
title: "A.6   Using the lastprivate Clause"
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
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# A.6   Using the lastprivate Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Korrigieren von der Ausführung hängt auch von dem Wert ab, den der letzten Iteration einer Schleife zu einer Variablen zuordnet.  Solche Programme müssen all diese Variablen wie Argumente an eine `lastprivate` Clause \([2.7.2.3 Abschnitt](../../parallel/openmp/2-7-2-3-lastprivate.md) auf Seite 27\) aufführen dass die Werte der Variablen identisch mit sind, wenn die Schleife sequenziell ausgeführt wird.  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 Im vorhergehenden Beispiel entspricht der Wert von `i` am Ende des parallelen Bereichs `n–1`, wie im sequenziellen Fall.