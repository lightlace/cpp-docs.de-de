---
title: "A.25   Examples of the copyprivate Data Attribute Clause"
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
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# A.25   Examples of the copyprivate Data Attribute Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Beispiel 1:** die `copyprivate` Clause \([2.7.2.8 Abschnitt](../../parallel/openmp/2-7-2-8-copyprivate.md) auf Seite 32\) kann verwendet werden, um die Werte zu übertragen, die durch einen einzelnen Thread direkt für alle Instanzen des privaten Variablen in anderen Threads abgerufen werden.  
  
```  
float x, y;  
#pragma omp threadprivate(x, y)  
  
void init( )   
{  
    float a;  
    float b;  
  
    #pragma omp single copyprivate(a,b,x,y)  
    {  
        get_values(a,b,x,y);  
    }  
  
    use_values(a, b, x, y);  
}  
```  
  
 Wenn Routine\-init aus einem seriellen Bereich aufgerufen wird, ist das Verhalten nicht durch das Vorhandensein der Direktiven betroffen.  Nach dem Aufruf der Routine *get\_values* durch einen Thread ausgeführt wurde, bewirkt, dass kein Thread bis das Konstrukt private Objekte, die von *a*, *b*, *x*und *y* festgelegt werden, in allen Threads sind mit dem Wert lesen definiert geworden.  
  
 **Beispiel 2:** im Gegensatz zum vorherigen Beispiel wird davon ausgegangen, dass das Lesen von einem bestimmten Thread ausgeführt werden muss, lautet der Masterthread.  In diesem Fall kann die `copyprivate`\-Klausel nicht verwendet werden, um die Übertragung direkt auszuführen, aber sie kann verwendet werden, um den Zugriff auf einen temporären freigegebenen Objekt zu gewähren.  
  
```  
float read_next( )   
{  
    float * tmp;  
    float return_val;  
  
    #pragma omp single copyprivate(tmp)  
    {  
        tmp = (float *) malloc(sizeof(float));  
    }  
  
    #pragma omp master  
    {  
        get_float( tmp );  
    }  
  
    #pragma omp barrier  
    return_val = *tmp;  
    #pragma omp barrier  
  
    #pragma omp single  
    {  
       free(tmp);  
    }  
  
    return return_val;  
}  
```  
  
 **Beispiel 3:** wird davon ausgegangen, dass die Anzahl der Sperren von Objekten, die innerhalb eines parallelen Bereichs benötigt werden, nicht vor dem Eingeben sie leicht ermittelt werden kann.  Die `copyprivate`\-Klausel kann verwendet werden, um den Zugriff auf Objekte die gemeinsame Sperre zu ermöglichen, die innerhalb von parallelen Bereichs zugeordnet sind.  
  
```  
#include <omp.h>  
  
omp_lock_t *new_lock()  
{  
    omp_lock_t *lock_ptr;  
  
    #pragma omp single copyprivate(lock_ptr)  
    {  
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));  
        omp_init_lock( lock_ptr );  
    }  
  
    return lock_ptr;  
}  
```