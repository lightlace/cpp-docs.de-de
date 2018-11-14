---
title: HUGE_VAL, _HUGE
ms.date: 11/04/2016
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
ms.openlocfilehash: 8f8342990ea62b368b46ed56f0697a844c755a61
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522128"
---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>Syntax

```

#include <math.h>
```

## <a name="remarks"></a>Hinweise

`HUGE_VAL` ist der größte darstellbare Double-Wert. Dieser Wert wird durch viele mathematische Laufzeitfunktionen zurückgegeben, wenn ein Fehler auftritt. Für einige Funktionen wird -`HUGE_VAL` zurückgegeben. `HUGE_VAL` wird als `_HUGE` definiert, aber die mathematischen Laufzeitfunktionen geben `HUGE_VAL` zurück. Verwenden Sie der Konsistenz wegen außerdem `HUGE_VAL` in Ihrem Code.

## <a name="see-also"></a>Siehe auch

[Globale Konstanten](../c-runtime-library/global-constants.md)