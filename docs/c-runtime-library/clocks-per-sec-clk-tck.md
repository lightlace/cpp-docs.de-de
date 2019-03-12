---
title: CLOCKS_PER_SEC, CLK_TCK
ms.date: 11/04/2016
f1_keywords:
- CLOCKS_PER_SEC
- CLK_TCK
helpviewer_keywords:
- CLOCKS_PER_SEC
- CLK_TCK constant
ms.assetid: bc285106-383d-44cb-91bf-276ad7de57bf
ms.openlocfilehash: eef065ac4fcedf13f3a5d54d4df0563fd04ef965
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750675"
---
# <a name="clockspersec-clktck"></a>CLOCKS_PER_SEC, CLK_TCK

## <a name="syntax"></a>Syntax

```
#include <time.h>
```

## <a name="remarks"></a>Anmerkungen

Die Zeit in Sekunden ist der von der `clock`-Funktion zurückgegebene Wert, geteilt durch `CLOCKS_PER_SEC`. `CLK_TCK` ist die Entsprechung, wird jedoch als veraltet eingestuft.

## <a name="see-also"></a>Siehe auch

[clock](../c-runtime-library/reference/clock.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)
