---
title: Noalias | Microsoft-Dokumentation
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
ms.openlocfilehash: 56ee12f65ff9efe9f3b048d061b80aef691eb0f2
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404394"
---
# <a name="noalias"></a>noalias

**Microsoft-spezifisch**

**Noalias** bedeutet, dass ein Funktionsaufruf nicht ändert oder sichtbaren globalen Zustand verweisen und nur den Speicher zeigt ändert *direkt* durch Zeigerparameter (Dereferenzierungen der ersten Ebene).

Wenn eine Funktion als Anmerkung versehen ist **Noalias**, der Optimierer kann davon ausgehen, dass zusätzlich zu den Parametern selbst nur auf oberster Ebene auf Dereferenzierungen der Zeigerparameter auf die verwiesen wird oder innerhalb der Funktion geändert werden. Der sichtbare globale Zustand ist der Satz aller Daten, die nicht außerhalb des Kompilierungsbereichs definiert werden oder auf die nicht außerhalb des Kompilierungsbereichs verwiesen wird, und ihre Adresse wird nicht akzeptiert. Der kompilierungsbereich umfasst alle Quelldateien ([/LTCG (Link-Time Code Generation)](../build/reference/ltcg-link-time-code-generation.md) erstellt) oder eine einzelne Quelldatei (nicht-**"/ LTCG"** erstellen).

Die **Noalias** -Anmerkung gilt nur innerhalb des Texts, der mit Anmerkungen versehenen Funktion. Markieren eine Funktion als **__declspec(noalias)** wirkt sich nicht auf das Aliasing von Zeigern, die von der Funktion zurückgegeben.

Eine andere Anmerkung, die Aliasing auswirken können, finden Sie unter [__declspec(restrict)](../cpp/restrict.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von **__declspec(noalias)**.

Wenn die Funktion `multiply` , dass mit Anmerkungen zugreift versehen **__declspec(noalias)**, weist den Compiler, dass diese Funktion den globalen Status außer durch die Zeiger in der Parameterliste nicht ändert.

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
