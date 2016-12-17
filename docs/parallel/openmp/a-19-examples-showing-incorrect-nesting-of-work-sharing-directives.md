---
title: "A.19   Examples Showing Incorrect Nesting of Work-sharing Directives"
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
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# A.19   Examples Showing Incorrect Nesting of Work-sharing Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Beispiele in diesem Abschnitt veranschaulichen die Schachtelungs Directive.  Weitere Informationen zu richtungweisende Schachtelung finden Sie unter [Abschnitt 2.9](../../parallel/openmp/2-9-directive-nesting.md) auf Seite 33.  
  
 Im folgenden Beispiel ist inkompatibel, da die inneren und äußeren `for`\-Direktive geschachtelt und demselben `parallel` die Direktive verbindlich sind für sind:  
  
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
  
 Die folgende dynamisch geschachtelte Version des obigen Beispiel ist auch nicht kompatibel:  
  
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
  
 Im folgenden Beispiel ist inkompatibel, da die `for` und `single`\-Direktive geschachtelt sind, und binden sie an denselben parallelen Bereich:  
  
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
  
 Im folgenden Beispiel ist inkompatibel, da `barrier`\-Direktive in `for` Deadlock führen kann:  
  
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
  
 Im folgenden Beispiel ist inkompatibel, da aufgrund eines Deadlocks `barrier` Fakten führt, dass nur ein Thread in den kritischen Abschnitt gleichzeitig eingegeben werden kann:  
  
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
  
 Im folgenden Beispiel ist inkompatibel, da aufgrund eines Deadlocks `barrier` Fakten, das nur ein Thread den `single`\-Abschnitt beschrieben:  
  
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