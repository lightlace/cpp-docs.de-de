---
title: A. 23 Beispiele für die ordered-Direktive | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec609a77e9bdc7cbdbb0822dfde0a88110ce0244
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405969"
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23   Beispiele für die ordered-Direktive

Es ist möglich, mehrere geordnete Abschnitten mit einem `for` angegeben mit der `ordered` Klausel. Im erste Beispiel ist nicht kompatibel, da die API gibt Folgendes an:

"Eine Iteration einer Schleife mit einer `for` Konstrukt muss nicht ausgeführt, die gleiche `ordered` Direktive mehr als einmal, und es muss nicht ausgeführt, mehr als eine `ordered` Richtlinie." (Finden Sie unter [Abschnitt 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) auf Seite "22")

In diesem Beispiel nicht kompatible führen alle Iterationen 2 geordnete Abschnitte:

```
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

Im folgenden Beispiel von kompatiblen eine `for` mit mehr als einem sortiert Abschnitt:

```
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```