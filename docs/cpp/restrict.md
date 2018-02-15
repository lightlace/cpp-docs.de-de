---
title: "Einschränken | Microsoft Docs"
ms.custom: 
ms.date: 02/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec1a54e9c4f235de4aad796586cd7be3e7ee592e
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2018
---
# <a name="restrict"></a>restrict

**Microsoft-spezifisch**

Bei Anwendung auf eine Funktionsdeklaration oder eine Definition, die einen Zeigertyp zurückgibt `restrict` teilt dem Compiler, dass die Funktion gibt ein Objekt zurück, die nicht *Alias*, d. h. eine beliebige andere Zeiger verweist. Dies kann der Compiler zusätzliche Optimierungen durchzuführen.

## <a name="syntax"></a>Syntax

> **__declspec(restrict)** *pointer_return_type* *function*();  
  
## <a name="remarks"></a>Hinweise

Der Compiler gibt Weiter `__declspec(restrict)`. Z. B. der CRT `malloc` Funktion verfügt über eine `__declspec(restrict)` Dekoration, und damit der Compiler geht davon aus, dass initialisierte Zeiger auf Speicheradressen von `malloc` sind ebenfalls nicht als Alias von zuvor vorhandenen Zeiger.

Der Compiler überprüft nicht, dass der zurückgegebene Zeiger nicht tatsächlich ein Alias zugeordnet ist. Es liegt in der Verantwortung des Entwicklers, sicherzustellen, dass das Programm einem Zeiger, der mit dem `restrict __declspec`-Modifizierer markiert ist, keinen Alias zuweist.  
  
Ähnliche Semantik für Variablen finden Sie unter [__restrict](../cpp/extension-restrict.md).
 
Eine andere Anmerkung, die für das Aliasing innerhalb einer Funktion angewendet wird, finden Sie unter [__declspec(noalias)](../cpp/noalias.md).
  
Informationen zu den **beschränken** Schlüsselwort, das Teil des C++ AMP wird finden Sie unter [einschränken (C++-AMP)](../cpp/restrict-cpp-amp.md).  
 
## <a name="example"></a>Beispiel  

Im folgende Beispiel veranschaulicht die Verwendung von `__declspec(restrict)`.

Wenn `__declspec(restrict)` wird angewendet auf eine Funktion, die einen Zeiger zurückgibt, das dem Compiler weist, dass der Arbeitsspeicher auf der Rückgabewert zeigt keinen Alias besitzt. In diesem Beispiel die Zeiger `mempool` und `memptr` sind global, damit der Compiler, dass der Arbeitsspeicher, die sie verweisen, nicht als Alias ist nicht sicher sein kann. Allerdings innerhalb verwendet werden `ma` und seine Aufrufer `init` auf eine Weise, die Arbeitsspeicher zurückgibt, die andernfalls von der Anwendung verwiesen wird, daher ist nicht `__decslpec(restrict)` wird verwendet, um den Optimierer helfen. Dieser Vorgang ähnelt, wie die CRT-Header Zuordnungsfunktionen wie z. B. ergänzen `malloc` mit `__declspec(restrict)` um anzugeben, dass sie stets Arbeitsspeicher zurückgeben, der einen Alias von vorhandenen Zeigern werden kann.

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

[Schlüsselwörter](../cpp/keywords-cpp.md)  
[__declspec](../cpp/declspec.md)  
[__declspec(noalias)](../cpp/noalias.md)  
