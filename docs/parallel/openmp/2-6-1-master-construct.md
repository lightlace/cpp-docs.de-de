---
title: 2.6.1 master-Konstrukt
ms.date: 11/04/2016
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
ms.openlocfilehash: 0501b1fdfbd36829cee2793fc0f7bb03daeda900
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475529"
---
# <a name="261-master-construct"></a>2.6.1 master-Konstrukt

Die **master** -Direktive identifiziert ein Konstrukt, das einem strukturierten Block gibt an, die durch die master-Thread des Teams ausgeführt wird. Die Syntax der **master** Richtlinie lautet wie folgt:

```
#pragma omp master new-linestructured-block
```

Andere Threads in das Team werden den zugeordneten strukturierten Block nicht ausgeführt werden. Es gibt keine implizite Hindernisse, die entweder zu Beginn oder nach Beendigung der master-Konstrukt.