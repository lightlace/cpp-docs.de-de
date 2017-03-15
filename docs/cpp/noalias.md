---
title: "noalias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noalias"
  - "noalias_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], noalias"
  - "noalias __declspec-Schlüsselwort"
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# noalias
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 `noalias` bedeutet, dass ein Funktionsaufruf den sichtbaren globalen Zustand nicht ändert oder darauf verweist und nur den Speicher ändert, auf den `directly` durch Zeigerparameter gezeigt wird \(Dereferenzierungen der ersten Ebene\).  
  
 Wenn eine Funktion als `noalias` kommentiert wird, kann der Optimierer davon ausgehen, dass zusätzlich zu den Parametern selbst innerhalb der Funktion nur auf Dereferenzierungen der ersten Ebene von Zeigerparametern verwiesen wird oder diese geändert werden.  Der sichtbare globale Zustand ist der Satz aller Daten, die nicht außerhalb des Kompilierungsbereichs definiert werden oder auf die nicht außerhalb des Kompilierungsbereichs verwiesen wird, und ihre Adresse wird nicht akzeptiert.  Der Kompilierungsbereich umfasst alle Quelldateien \([\/LTCG \(Code zur Verknüpfungszeit generieren\)](../build/reference/ltcg-link-time-code-generation.md)\-Builds\) oder eine einzelne Quelldatei \(Nicht\-**\/LTCG**\-Build\).  
  
## Beispiel  
 Das folgende Beispiel zeigt die Verwendung von `__declspec(restrict)` und `__declspec(noalias)`.  Normalerweise ist der Arbeitsspeicher, der von `malloc` zurückgegeben wird, `restrict` und `noalias`, da die CRT\-Header entsprechend ergänzt werden.  
  
 In diesem Beispiel sind jedoch die Zeiger `mempool` und `memptr` global, daher kann der Compiler nicht sicher davon ausgehen, dass auf den Arbeitsspeicher nicht Aliasing durchgeführt wird.  Durch Ergänzen der Funktionen, die Zeiger zurückgeben, mit `__declspec(restrict)` wird der Compiler angewiesen, dass für den Arbeitsspeicher, auf den der Rückgabewert zeigt, kein Aliasing durchgeführt wird.  
  
 Durch Ergänzen der Funktion im Beispiel, die auf Arbeitsspeicher zugreift, mit `__declspec(noalias)` wird der Compiler angewiesen, dass diese Funktion den globalen Zustand nicht beeinträchtigt, außer durch die Zeiger in ihrer Parameterliste .  
  
```  
// declspec_noalias.c   
#include <stdio.h>  
#include <stdlib.h>  
  
#define M 800  
#define N 600  
#define P 700  
  
float * mempool, * memptr;  
  
__declspec(restrict) float * ma(int size)  
{  
    float * retval;  
    retval = memptr;  
    memptr += size;  
    return retval;  
}  
  
__declspec(restrict) float * init(int m, int n)  
{  
    float * a;  
    int i, j;  
    int k=1;  
  
    a = ma(m * n);  
    if (!a) exit(1);  
    for (i=0; i<m; i++)  
        for (j=0; j<n; j++)  
            a[i*n+j] = 0.1/k++;  
    return a;  
}  
  
__declspec(noalias) void multiply(float * a, float * b, float * c)  
{  
    int i, j, k;  
  
    for (j=0; j<P; j++)  
        for (i=0; i<M; i++)  
            for (k=0; k<N; k++)  
                c[i * P + j] =   
                          a[i * N + k] *   
                          b[k * P + j];  
}  
  
int main()  
{  
    float * a, * b, * c;  
  
    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));  
  
    if (!mempool)   
    {  
        puts("ERROR: Malloc returned null");  
        exit(1);  
    }  
  
    memptr = mempool;  
    a = init(M, N);  
    b = init(N, P);  
    c = init(M, P);  
  
    multiply(a, b, c);  
}  
```  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)