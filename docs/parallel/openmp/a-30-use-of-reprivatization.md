---
title: A.30   Verwenden der erneuten Privatisierung
ms.date: 11/04/2016
ms.assetid: 26529090-6c39-40f2-b806-e12374d6b5f8
ms.openlocfilehash: dc1d142a282fe6bb55c9cc512e6a6e8155b286e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437322"
---
# <a name="a30---use-of-reprivatization"></a>A.30   Verwenden der erneuten Privatisierung

Das folgende Beispiel zeigt der erneuten Privatisierung von Variablen. Private Variablen können markiert werden `private` erneut in einer geschachtelten-Direktive. Sie müssen nicht in den einschließenden parallelen Bereich gemeinsam genutzt werden.

```
int i, a;
...
#pragma omp parallel private(a)
{
  ...
  #pragma omp parallel for private(a)
  for (i=0; i<10; i++)
     {
       ...
     }
}
```