---
title: _locking-Konstanten
ms.date: 11/04/2016
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
ms.openlocfilehash: d559a68e8fede6e0b6dd40505a041b14da703681
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738489"
---
# <a name="locking-constants"></a>_locking-Konstanten

## <a name="syntax"></a>Syntax

```
#include <sys/locking.h>
```

## <a name="remarks"></a>Anmerkungen

Das *mode*-Argument im Aufruf der `_locking`-Funktion gibt die auszuführende Sperraktion an.

Das *mode*-Argument muss eine der folgenden Manifestkonstanten sein.

|||
|-|-|
| `_LK_LOCK`  | Sperrt die angegebenen Bytes. Wenn die Bytes nicht gesperrt werden können, führt die Funktion nach 1 Sekunde einen neuen Versuch durch. Wenn nach 10 Versuchen die Bytes nicht gesperrt werden können, gibt die Funktion einen Fehler zurück.  |
| `_LK_RLCK`  | Wie in `_LK_LOCK`.  |
|`_LK_NBLCK`  | Sperrt die angegebenen Bytes. Wenn die Bytes nicht gesperrt werden können, gibt die Funktion einen Fehler zurück.  |
| `_LK_NBRLCK`  | Wie in `_LK_NBLCK`.  |
| `_LK_UNLCK`  | Entsperrt die angegebenen Bytes. (Die Bytes müssen zuvor gesperrt worden sein.)  |

## <a name="see-also"></a>Siehe auch

[_locking](../c-runtime-library/reference/locking.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)
