---
title: 2.6.6 ordered-Konstrukt
ms.date: 11/04/2016
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
ms.openlocfilehash: fe6ad4adf2a4fcccfefe3c3585d9c88c0a118931
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615799"
---
# <a name="266-ordered-construct"></a>2.6.6 ordered-Konstrukt

Die folgenden vor einem strukturierten Block ein **sortiert** Richtlinie ausgeführt wird, in der Reihenfolge, in denen Iterationen in einer sequenziellen Schleife ausgeführt. Die Syntax der **sortiert** Richtlinie lautet wie folgt:

```
#pragma omp ordered new-linestructured-block
```

Ein **sortiert** Richtlinie im dynamischen Wertebereich liegen eine **für** oder **für parallele** zu erstellen. Die **für** oder **für parallele** , der die Richtlinie der **sortiert** Konstrukt Bindungen müssen einen **sortiert** -Klausel angegeben, wie in beschrieben [Abschnitt 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) auf Seite "11". Bei der Ausführung eine **für** oder **für parallele** erstellen, mit eine **sortiert** -Klausel **sortiert** Konstrukte ausgeführt werden, ausschließlich in der die Reihenfolge, in dem sie in eine sequenzielle Ausführung der Schleife ausgeführt werden sollen.

Einschränkungen für die **sortiert** Richtlinie lauten wie folgt:

- Eine Iteration einer Schleife mit einem **für** Konstrukt muss nicht die gleiche ordered-Direktive mehr als einmal ausgeführt, und er nicht ausgeführt werden muss mehr als eine **sortiert** Richtlinie.