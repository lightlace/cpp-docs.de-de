---
title: A.24   Beispiel für die private-Klausel
ms.date: 11/04/2016
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
ms.openlocfilehash: facf5b953b26d284f6bfed4f35a9162f6d2bf212
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552957"
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