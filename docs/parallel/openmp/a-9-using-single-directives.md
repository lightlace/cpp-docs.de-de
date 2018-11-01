---
title: A.9   Verwenden einzelner Direktiven
ms.date: 11/04/2016
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
ms.openlocfilehash: 51a2a3438ae5abc9d24c160a986c8ea04b77c4bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501308"
---
# <a name="a9---using-single-directives"></a>A.9   Verwenden einzelner Direktiven

Das folgende Beispiel zeigt die `single` Richtlinie ([Abschnitt 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) auf Seite 15). Im Beispiel ist nur ein Thread (normalerweise der erste Thread, der erkennt die `single` Richtlinie) gibt die Meldung von Fortschritt. Der Benutzer muss keine Annahmen zu welchem Thread ausgeführt, wird die `single` Abschnitt. Alle anderen Threads werden übersprungen. die `single` aus, und beenden Sie die Barriere am Ende der `single` zu erstellen. Wenn andere Threads fortgesetzt werden können, ohne zu warten, für die Threadausführung den `single` Abschnitt eine `nowait` Klausel kann angegeben werden, auf die `single` Richtlinie.

```
#pragma omp parallel
{
    #pragma omp single
        printf_s("Beginning work1.\n");
    work1();
    #pragma omp single
        printf_s("Finishing work1.\n");
    #pragma omp single nowait
        printf_s("Finished work1 and beginning work2.\n");
    work2();
}
```