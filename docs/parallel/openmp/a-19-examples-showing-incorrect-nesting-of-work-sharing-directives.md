---
title: A.19   Beispiele für falsche Verschachtelung von Arbeitsteilungsdirektiven
ms.date: 11/04/2016
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
ms.openlocfilehash: 5be09dd3282260dabc2ef30dafc249539d6a6418
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501945"
---
# <a name="a19---examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19   Beispiele für falsche Verschachtelung von Arbeitsteilungsdirektiven

In die Beispielen in diesem Abschnitt veranschaulichen die Regeln für die Richtlinie schachteln. Weitere Informationen für die Direktive Schachtelung finden Sie unter [Abschnitt 2.9](../../parallel/openmp/2-9-directive-nesting.md) auf Seite 33.

Im folgende Beispiel nicht konform ist. da die inneren und äußeren `for` Anweisungen geschachtelt sind und auf die gleiche Bindung `parallel` Richtlinie:

```
void wrong1(int n)
{
  #pragma omp parallel default(shared)
  {
      int i, j;
      #pragma omp for
      for (i=0; i<n; i++) {
          #pragma omp for
              for (j=0; j<n; j++)
                 work(i, j);
     }
   }
}
```

Die folgende dynamisch geschachtelte Version des obigen Beispiels ist auch nicht kompatibel:

```
void wrong2(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++)
        work1(i, n);
  }
}

void work1(int i, int n)
{
  int j;
  #pragma omp for
    for (j=0; j<n; j++)
      work2(i, j);
}
```

Im folgende Beispiel nicht konform ist da die `for` und `single` Anweisungen geschachtelt sind und sie an der gleichen Region für die parallele binden:

```
void wrong3(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        #pragma omp single
          work(i);
      }
  }
}
```

Im folgende Beispiel nicht konform ist. da eine `barrier` -Direktive innerhalb einer `for` kann zu Deadlocks führen:

```
void wrong4(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        work1(i);
        #pragma omp barrier
        work2(i);
      }
  }
}
```

Im folgende Beispiel nicht konform ist. da der `barrier` Deadlock führt aufgrund der Tatsache, dass jeweils nur ein Thread den kritischen Abschnitt eingegeben werden kann:

```
void wrong5()
{
  #pragma omp parallel
  {
    #pragma omp critical
    {
       work1();
       #pragma omp barrier
       work2();
    }
  }
}
```

Im folgende Beispiel nicht konform ist. da die `barrier` Deadlock führt aufgrund der Tatsache, dass nur ein Thread ausgeführt wird die `single` Abschnitt:

```
void wrong6()
{
  #pragma omp parallel
  {
    setup();
    #pragma omp single
    {
      work1();
      #pragma omp barrier
      work2();
    }
    finish();
  }
}
```