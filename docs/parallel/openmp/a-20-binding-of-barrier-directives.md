---
title: A.20 Bindung der Barriere Direktiven | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1123ab0b4d406a613176dfcd50f459d089e45d9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691409"
---
# <a name="a20---binding-of-barrier-directives"></a>A.20   Bindung von barrier-Direktiven
Die direktivenbindung Regeln Aufruf für eine **Barriere** Richtlinie zum Binden an der nächsten einschließenden `parallel` Richtlinie. Weitere Informationen für direktivenbindung finden Sie unter [Abschnitt 2.8](../../parallel/openmp/2-8-directive-binding.md) auf Seite "32".  
  
 Im folgenden Beispiel der Aufruf aus *main* auf *sub2* kompatibel ist da die **Barriere** (in *sub3*) bindet an den parallelen Bereich in *sub2*. Der Aufruf von *main* auf *sub1* kompatibel ist da die **Barriere** bindet an den parallelen Bereich im Unterroutine *sub2*.  Der Aufruf von *main* auf *sub3* kompatibel ist da die **Barriere** Bindung erfolgt nicht zu einer beliebigen parallel Region und wird ignoriert. Beachten Sie, dass die **Barriere** nur synchronisiert das Team von Threads in der einschließenden parallelen Bereich und nicht alle Threads in erstellten *sub1*.  
  
```  
int main()  
{  
    sub1(2);  
    sub2(2);  
    sub3(2);  
}  
  
void sub1(int n)  
{  
    int i;  
    #pragma omp parallel private(i) shared(n)  
    {  
        #pragma omp for  
        for (i=0; i<n; i++)  
            sub2(i);  
    }  
}  
  
void sub2(int k)  
{  
     #pragma omp parallel shared(k)  
     sub3(k);  
}  
  
void sub3(int n)  
{  
    work(n);  
    #pragma omp barrier  
    work(n);  
}  
```