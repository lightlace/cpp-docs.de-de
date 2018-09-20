---
title: A. 20 Bindung von Barrier-Direktiven | Microsoft-Dokumentation
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
ms.openlocfilehash: 628920caa6a122230f42394cc757e3abdb1874cd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381308"
---
# <a name="a20---binding-of-barrier-directives"></a>A.20   Bindung von barrier-Direktiven

Die direktivenbindung Regeln-Aufruf für eine **Barriere** Richtlinie zum Binden an die nächste einschließende `parallel` Richtlinie. Weitere Informationen zu direktivenbindung, finden Sie unter [Abschnitt 2.8](../../parallel/openmp/2-8-directive-binding.md) auf Seite "32".

Im folgenden Beispiel den Aufruf von *main* zu *sub2* ist kompatibel, da die **Barriere** (in *sub3*) bindet an den parallelen Bereich in *sub2*. Den Aufruf von *main* zu *sub1* ist kompatibel, da die **Barriere** bindet an die parallelen Bereichs in der Unterroutine *sub2*.  Den Aufruf von *main* zu *sub3* ist kompatibel, da die **Barriere** Bindung erfolgt nicht in einer beliebigen Region parallel und wird ignoriert. Beachten Sie, dass die **Barriere** synchronisiert nur das Team von Threads in der einschließenden parallelen Bereich und nicht alle Threads in erstellten *sub1*.

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