---
title: Signalaktionskonstanten
ms.date: 11/04/2016
f1_keywords:
- SIG_IGN
- SIG_DFL
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
ms.openlocfilehash: 4ff79626d576a05744336d36f99caf95d9b9902d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743875"
---
# <a name="signal-action-constants"></a>Signalaktionskonstanten

Die Aktion, die unabhängig des Werts von `func` ausgeführt wird, wenn das Interruptsignal empfangen wird.

## <a name="syntax"></a>Syntax

```
#include <signal.h>
```

## <a name="remarks"></a>Anmerkungen

Das `func`-Argument muss entweder eine Funktionsadresse oder eine der unten aufgelisteten und in SIGNAL.H definierten Manifestkonstanten sein.

|||
|-|-|
| `SIG_DFL`  | Systemstandardantwort wird verwendet. Wenn das aufrufende Programm Datenstrom-E/A verwendet, werden von der Laufzeitbibliothek erstellte Puffer nicht geleert.  |
| `SIG_IGN`  | Ignoriert das Interruptsignal. Dieser Wert sollte nie `SIGFPE` zugewiesen werden, da der Gleitkommazustand des Prozesses undefiniert bleibt.  |
| `SIG_SGE`  | Zeigt an, dass ein Fehler in dem Signal aufgetreten ist.  |
| `SIG_ACK`  | Gibt an, dass eine Bestätigung empfangen wurde.  |
| `SIG_ERR`  | Ein Rückgabetyp aus einem Signal, der angibt, das ein Fehler aufgetreten ist.  |

## <a name="see-also"></a>Siehe auch

[signal](../c-runtime-library/reference/signal.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)
