---
title: Signalkonstanten
ms.date: 11/04/2016
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
ms.openlocfilehash: 1046a12fa0f250b348e6ff171c8865e3eb5ff4b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482661"
---
# <a name="signal-constants"></a>Signalkonstanten

## <a name="syntax"></a>Syntax

```
#include <signal.h>
```

## <a name="remarks"></a>Hinweise

Das `sig`-Argument muss eine der unten aufgelisteten (und in SIGNAL.H definierten) Manifestkonstanten sein.

|||
|-|-|
|SIGABRT|Nicht ordnungsgemäße Beendigung. Die Standardaktion beendet das aufrufende Programm mit Exitcode 3.  |
|SIGABRT_COMPAT|Identisch mit SIGABRT. Zur Kompatibilität mit anderen Plattformen.  |
|SIGFPE|Gleitkommafehler, z.B. Überlauf, Division durch 0 (null) oder eine ungültige Operation. Die Standardaktion beendet das aufrufende Programm.  |
|SIGILL|Ungültige Anweisung. Die Standardaktion beendet das aufrufende Programm.  |
|SIGINT|STRG+C-Unterbrechung. Die Standardaktion beendet das aufrufende Programm mit Exitcode 3.  |
|SIGSEGV|Ungültiger Speicherzugriff. Die Standardaktion beendet das aufrufende Programm.  |
|SIGTERM|An das Programm gesendete Beendigungsanforderung. Die Standardaktion beendet das aufrufende Programm mit Exitcode 3.  |
|SIG_ERR|Ein Rückgabetyp aus einem Signal, der angibt, das ein Fehler aufgetreten ist.  |

## <a name="see-also"></a>Siehe auch

[signal](../c-runtime-library/reference/signal.md)<br/>
[raise](../c-runtime-library/reference/raise.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)