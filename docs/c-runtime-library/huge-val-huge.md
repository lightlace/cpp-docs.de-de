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
ms.openlocfilehash: b1d9b099684d9671a60dd1afb1e6692e3c0d2a65
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220477"
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
