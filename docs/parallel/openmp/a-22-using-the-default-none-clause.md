---
title: "A.22   Using the default(none) Clause"
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
ms.assetid: a3fa4e62-1e92-4896-ae3f-be268067d917
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# A.22   Using the default(none) Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel wird die Variablen, die von der `default(none)`\-Klausel von denen betroffen sind, die keine sind:  
  
```  
// openmp_using_clausedefault.c  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int x, y, z[1000];  
#pragma omp threadprivate(x)  
  
void fun(int a) {  
   const int c = 1;  
   int i = 0;  
  
   #pragma omp parallel default(none) private(a) shared(z)  
   {  
      int j = omp_get_num_thread();  
             //O.K.  - j is declared within parallel region  
      a = z[j];       // O.K.  - a is listed in private clause  
                      //      - z is listed in shared clause  
      x = c;          // O.K.  - x is threadprivate  
                      //      - c has const-qualified type  
      z[i] = y;       // C3052 error - cannot reference i or y here  
  
      #pragma omp for firstprivate(y)  
         for (i=0; i<10 ; i++) {  
            z[i] = y;  // O.K. - i is the loop control variable  
                       // - y is listed in firstprivate clause  
          }  
       z[i] = y;   // Error - cannot reference i or y here  
   }  
}  
```  
  
 Weitere Informationen über die `default`\-Klausel finden Sie unter [2.7.2.5 Abschnitt](../../parallel/openmp/2-7-2-5-default.md) auf Seite 28.