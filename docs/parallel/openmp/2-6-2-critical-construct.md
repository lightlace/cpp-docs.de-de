---
title: 2.6.2 critical-Konstrukt
ms.date: 11/04/2016
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
ms.openlocfilehash: dcc0e6144be5daee2a225cda621db818e5a38e2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539073"
---
# <a name="262-critical-construct"></a>2.6.2 critical-Konstrukt

Die **kritische** -Direktive identifiziert ein Konstrukt, die Ausführung von einem zugeordneten strukturierten Block auf einen einzelnen Thread zu einem Zeitpunkt beschränkt. Die Syntax der **kritische** Richtlinie lautet wie folgt:

```
#pragma omp critical [(name)]  new-linestructured-block
```

Eine optionale *Namen* kann zum Identifizieren des kritischen Bereichs verwendet werden. Bezeichner, die zum Identifizieren von eines kritischen Bereichs verfügen über eine externe Bindung, und in einem Namespace ist unabhängig von den Namespaces, die von Bezeichnungen, Tags, Mitglieder und wie gewöhnliche Bezeichner verwendet werden.

Ein Thread wartet am Anfang des einem kritischen Bereich, bis kein anderer Thread einen kritischen Bereich (eine beliebige Stelle im Programm), mit dem gleichen Namen ausgeführt wird. Alle unbenannten **kritische** Anweisungen in den nicht angegebenen Namen zugeordnet.