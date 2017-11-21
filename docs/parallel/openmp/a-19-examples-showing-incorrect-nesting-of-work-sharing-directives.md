---
title: A.19 Beispiele, falsche Schachtelung von Direktiven Arbeit Freigabe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1cc5ed3a3a5ddd4117a3332703613a8d525853a8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="a19---examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19   Beispiele für falsche Verschachtelung von Arbeitsteilungsdirektiven
In den Beispielen in diesem Abschnitt wird die Richtlinie schachteln Regeln. Weitere Informationen über die Richtlinie Schachtelung, finden Sie unter [Abschnitt 2.9](../../parallel/openmp/2-9-directive-nesting.md) auf Seite "33".  
  
 Im folgende Beispiel wird nicht kompatible da inneren und äußeren `for` -Direktiven geschachtelt sind, und Binden an die gleiche `parallel` Richtlinie:  
  
```  
void wrong1(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
      int i, j;  
      #pragma omp for  
      for (i=0; i<n; i++) {  
          #pragma omp for  
              for (j=0; j<n; j++)  
                 work(i, j);  
     }  
   }  
}  
```  
  
 Die folgende dynamisch geschachtelte Version des obigen Beispiels ist ebenfalls nicht kompatibel:  
  
```  
void wrong2(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++)  
        work1(i, n);  
  }  
}  
  
void work1(int i, int n)  
{  
  int j;  
  #pragma omp for  
    for (j=0; j<n; j++)  
      work2(i, j);  
}  
```  
  
 Im folgende Beispiel wird nicht kompatible da die `for` und `single` -Direktiven geschachtelt werden und sie an der gleichen Region für die parallele binden:  
  
```  
void wrong3(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        #pragma omp single  
          work(i);  
      }  
  }  
}  
```  
  
 Das folgende Beispiel ist nicht kompatibel da eine `barrier` -Anweisung innerhalb einer `for` Deadlock führen können:  
  
```  
void wrong4(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        work1(i);  
        #pragma omp barrier  
        work2(i);  
      }  
  }  
}  
```  
  
 Im folgende Beispiel nicht konform ist. da die `barrier` Deadlock führt darauf zurückzuführen, dass jeweils nur ein Thread den kritischen Abschnitt eingeben kann:  
  
```  
void wrong5()  
{  
  #pragma omp parallel  
  {  
    #pragma omp critical  
    {  
       work1();  
       #pragma omp barrier  
       work2();  
    }  
  }  
}  
```  
  
 Im folgende Beispiel wird nicht kompatible da die `barrier` Deadlock führt darauf zurückzuführen, dass nur ein Thread ausgeführt wird die `single` Abschnitt:  
  
```  
void wrong6()  
{  
  #pragma omp parallel  
  {  
    setup();  
    #pragma omp single  
    {  
      work1();  
      #pragma omp barrier  
      work2();  
    }  
    finish();  
  }  
}  
```