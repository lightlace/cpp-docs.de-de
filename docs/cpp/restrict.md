---
title: restrict
ms.date: 02/09/2018
f1_keywords:
- restrict_cpp
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
ms.openlocfilehash: 40c1c05ca72f639829f2d3658497b0e9f3199640
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403372"
---
# <a name="restrict"></a>restrict

**Microsoft-spezifisch**

Bei Anwendung auf eine Deklaration oder Definition, die einen Zeigertyp zurückgibt **einschränken** informiert den Compiler, dass die Funktion gibt ein Objekt zurück, der nicht *Alias*, d. h. auf die verwiesen wird durch einen anderen Zeiger. Dies kann der Compiler weitere Optimierungen auszuführen.

## <a name="syntax"></a>Syntax

> **__declspec(restrict)** *pointer_return_type* *function*();

## <a name="remarks"></a>Hinweise

Der Compiler gibt **__declspec(restrict)**. Z. B. die CRT `malloc` Funktion verfügt über eine **__declspec(restrict)** Dekoration, und damit der Compiler geht davon aus, dass initialisierte Zeiger auf Speicheradressen von `malloc` sind ebenfalls nicht mit einem Alias versehen, indem zuvor vorhandenen Zeiger.

Der Compiler überprüft nicht, dass der zurückgegebene Zeiger nicht tatsächlich mit einem Alias versehen ist. Es ist Aufgabe des Entwicklers, um sicherzustellen, dass das Programm ist, keinen alias einen Zeiger mit markiert die **einschränken __declspec** Modifizierer.

Ähnliche Semantik für Variablen finden Sie unter ["__restrict"](../cpp/extension-restrict.md).

Eine andere Anmerkung, die für das Aliasing innerhalb einer Funktion angewendet wird, finden Sie unter [__declspec(noalias)](../cpp/noalias.md).

Informationen zu den **einschränken** Schlüsselwort, das Teil des C++ AMP ist, finden Sie unter [einschränken (C++-AMP)](../cpp/restrict-cpp-amp.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von **__declspec(restrict)**.

Wenn **__declspec(restrict)** gilt für eine Funktion, die einen Zeiger zurückgibt, das dem Compiler weist, dass der Arbeitsspeicher, die auf den Rückgabewert zeigt nicht mit einem Alias versehen ist. In diesem Beispiel die Zeiger `mempool` und `memptr` sind global, damit der Compiler kann nicht sicher sein, dass der Arbeitsspeicher, die sie verweisen auf nicht mit einem Alias versehen ist. Sie werden jedoch in verwendet `ma` und dessen Aufrufer `init` auf eine Weise, die Arbeitsspeicher zurückgibt, die andernfalls von der Anwendung, also nicht verwiesen wird **__decslpec(restrict)** wird verwendet, um den Optimierer. Dies ist ähnlich wie die CRT-Header Zuordnungsfunktionen wie z. B. ergänzen `malloc` mit **__declspec(restrict)** um anzugeben, dass sie immer Speicher zurück, der mit einem Alias versehen von vorhandenen Zeigern werden nicht möglich.

```C
// declspec_restrict.c
// Compile with: cl /W4 declspec_restrict.c
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
            a[i*n+j] = 0.1f/k++;
    return a;
}

void multiply(float * a, float * b, float * c)
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

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[__declspec](../cpp/declspec.md)<br/>
[__declspec(noalias)](../cpp/noalias.md)
