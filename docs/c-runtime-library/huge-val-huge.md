---
title: HUGE_VAL, _HUGE
ms.date: 11/04/2016
api_name:
- _HUGE
api_location:
- msvcrt.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _HUGE
- HUGE_VAL
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
ms.openlocfilehash: 3a0469b7158e765b1b1c6f34cb01c0e90beb1401
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940263"
---
# <a name="huge_val-_huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>Syntax

```
#include <math.h>
```

## <a name="remarks"></a>Anmerkungen

`HUGE_VAL` ist der größte darstellbare Double-Wert. Dieser Wert wird durch viele mathematische Laufzeitfunktionen zurückgegeben, wenn ein Fehler auftritt. Für einige Funktionen wird -`HUGE_VAL` zurückgegeben. `HUGE_VAL` wird als `_HUGE` definiert, aber die mathematischen Laufzeitfunktionen geben `HUGE_VAL` zurück. Verwenden Sie der Konsistenz wegen außerdem `HUGE_VAL` in Ihrem Code.

## <a name="see-also"></a>Siehe auch

[Globale Konstanten](../c-runtime-library/global-constants.md)
