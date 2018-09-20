---
title: A. 24 Beispiel für die private-Klausel | Microsoft-Dokumentation
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
ms.openlocfilehash: df2efc9fe111fa6e8d0b0507eceb20f07f48b02d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416239"
---
# <a name="a24---example-of-the-private-clause"></a>A.24   Beispiel für die private-Klausel

Die `private` Klausel ([Abschnitt 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) auf Seite 25) eines parallelen Bereichs ist nur für den lexikalischen Wertebereich des Bereichs, nicht für den dynamischen Wertebereich des Bereichs.  Aus diesem Grund in der folgenden, jede Verwendung der Variablen Beispiel *eine* innerhalb der `for` Schleife in der Routine *f* bezieht sich auf eine private Kopie des *eine*, zwar eine Verwendung in Routine *g* verweist auf die globale *eine*.

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