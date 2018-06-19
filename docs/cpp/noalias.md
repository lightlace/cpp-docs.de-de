---
title: Noalias | Microsoft Docs
ms.custom: ''
ms.date: 02/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noalias_cpp
dev_langs:
- C++
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cbb5c1b4162f3326aade092c7e20ca42a825d13
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420118"
---
# <a name="noalias"></a>noalias

**Microsoft-spezifisch**

`noalias` bedeutet, dass ein Funktionsaufruf nicht ändert oder sichtbaren globalen Zustand verweisen und nur den Speicher ändert *direkt* durch Zeigerparameter (Dereferenzierungen der ersten Ebene).

Wenn eine Funktion als `noalias` kommentiert wird, kann der Optimierer davon ausgehen, dass zusätzlich zu den Parametern selbst innerhalb der Funktion nur auf Dereferenzierungen der ersten Ebene von Zeigerparametern verwiesen wird oder diese geändert werden. Der sichtbare globale Zustand ist der Satz aller Daten, die nicht außerhalb des Kompilierungsbereichs definiert werden oder auf die nicht außerhalb des Kompilierungsbereichs verwiesen wird, und ihre Adresse wird nicht akzeptiert. Kompilierung bezieht sich auf alle Quelldateien ([/LTCG (Link-Time Code Generation)](../build/reference/ltcg-link-time-code-generation.md) erstellt) oder eine einzelne Quelldatei (nicht -**/LTCG** erstellen).

Die `noalias` -Anmerkung gilt nur innerhalb eines Texts der mit Anmerkung versehenen Funktion. Markieren eine Funktion als `__declspec(noalias)` wirkt sich nicht auf das Aliasing von Zeigern, die von der Funktion zurückgegeben.

Eine andere Anmerkung, die Aliasing auswirken kann, finden Sie unter [__declspec(restrict)](../cpp/restrict.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel veranschaulicht die Verwendung von `__declspec(noalias)`.

Wenn die Funktion `multiply` , dass zugreift kommentiert wird `__declspec(noalias)`, es weist den Compiler, dass diese Funktion den globalen Status außer durch die Zeiger in der Parameterliste nicht verändert wird.

```C
// declspec_noalias.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

float * init(int m, int n)
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

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)  
[Schlüsselwörter](../cpp/keywords-cpp.md)  
[__declspec(restrict)](../cpp/restrict.md)  
