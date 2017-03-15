---
title: "A.24   Example of the private Clause"
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
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# A.24   Example of the private Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `private` Clause \([2.7.2.1 Abschnitt](../../parallel/openmp/2-7-2-1-private.md) auf Seite 25\) eines parallelen Bereichs ist nur wirksam ist für den lexikalischen Wertebereich des Bereichs, für den keine dynamischen Wertebereich des Bereichs.  Daher im folgende Beispiel verwendet einen beliebigen *a*\-Variable aus der `for` innerhalb der Schleife in der Routine *f* verweist eine private Kopie von *A*, während eine Verwendung in Routine *g* das globale *A*verweist *.*  
  
```  
int a;  
  
void f(int n)   
{  
    a = 0;  
  
    #pragma omp parallel for private(a)  
    for (int i=1; i<n; i++)   
    {  
        a = i;  
        g(i, n);  
        d(a);     // Private copy of "a"  
        ...  
    }  
    ...  
  
void g(int k, int n)   
{  
    h(k,a); // The global "a", not the private "a" in f  
}  
```