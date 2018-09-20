---
title: A. 9 Verwenden einzelner Direktiven | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a3a201450d54355aa96f0ea712ad9fa0f70f63f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448089"
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