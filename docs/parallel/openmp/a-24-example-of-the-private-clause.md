---
title: Beispiel für die private-Klausel A.24 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f8d07f2d95b565077f5dfd78fdc4ff6edf30216
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="a24---example-of-the-private-clause"></a>A.24   Beispiel für die private-Klausel
Die `private` -Klausel ([Abschnitt 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) auf der Seite "25") eines parallelen Bereichs ist nur gültig für den lexikalischen Wertebereich des Bereichs, nicht für den dynamischen Wertebereich des Bereichs.  Aus diesem Grund im Beispiel, das folgt, jede Verwendung der Variablen *eine* innerhalb der `for` Schleife in der Routine *f* bezieht sich auf eine private Kopie *eine*, dagegen eine Verwendung in Routine *g* verweist auf die globale *eine*.  
  
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