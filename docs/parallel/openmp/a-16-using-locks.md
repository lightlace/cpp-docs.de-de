---
title: "A.16   Using Locks"
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
ms.assetid: 873bf32b-6cfe-4ce1-b994-bef80b50f399
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# A.16   Using Locks
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel \(für [Abschnitt 3.2](../../parallel/openmp/3-2-lock-functions.md) auf Seite 41\) beachten Sie, dass das Argument in den Typ`omp_lock_t`Funktionen Sperren sollte und dass keine Notwendigkeit vorliegt, sie zu leeren.  Die Sperren Funktionen führen dazu, dass die Threads im Leerlauf befinden, während sie auf den ersten Eintrag kritischen Abschnitt, aber andere Aufgaben zu erledigen beim Warten auf Eingabe an den zweiten.  Die `omp_set_lock`\-Funktion blockiert, aber die `omp_test_lock`\-Funktion ist dies nicht der Fall. Dadurch kann die Arbeit im Schritt \(\) ausgeführt werden sollen.  
  
## Beispiel  
  
### Code  
  
```  
// omp_using_locks.c  
// compile with: /openmp /c  
#include <stdio.h>  
#include <omp.h>  
  
void work(int);  
void skip(int);  
  
int main() {  
   omp_lock_t lck;  
   int id;  
  
   omp_init_lock(&lck);  
   #pragma omp parallel shared(lck) private(id)  
   {  
      id = omp_get_thread_num();  
  
      omp_set_lock(&lck);  
      printf_s("My thread id is %d.\n", id);  
  
      // only one thread at a time can execute this printf  
      omp_unset_lock(&lck);  
  
      while (! omp_test_lock(&lck)) {  
         skip(id);   // we do not yet have the lock,  
                     // so we must do something else   
      }  
      work(id);     // we now have the lock  
                    // and can do the work   
      omp_unset_lock(&lck);  
   }  
   omp_destroy_lock(&lck);  
}  
```