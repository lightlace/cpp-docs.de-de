---
title: noalias
ms.date: 02/09/2018
f1_keywords:
- noalias_cpp
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
ms.openlocfilehash: 2eceffd10f97615859918991320ceebf577d094c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377438"
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

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[__declspec(restrict)](../cpp/restrict.md)
