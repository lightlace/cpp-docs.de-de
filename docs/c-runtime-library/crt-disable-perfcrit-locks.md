---
title: _CRT_DISABLE_PERFCRIT_LOCKS
ms.date: 11/04/2016
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
ms.openlocfilehash: 475cc57b5b47f5abf8c268db3acf9e727ce6a743
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593461"
---
# <a name="crtdisableperfcritlocks"></a>_CRT_DISABLE_PERFCRIT_LOCKS

Deaktiviert die leistungskritische Sperre bei E/A-Vorgängen.

## <a name="syntax"></a>Syntax

```
#define _CRT_DISABLE_PERFCRIT_LOCKS
```

## <a name="remarks"></a>Hinweise

Durch die Definition dieses Symbols kann die Leistung in Singlethread-E/A-gebundenen Programmen verbessert werden, indem bei allen E/A-Vorgängen die Annahme eines Singlethread-E/A-Modells erzwungen wird. Weitere Informationen finden Sie unter [Leistung von Multithreadbibliotheken](../c-runtime-library/multithreaded-libraries-performance.md).

## <a name="see-also"></a>Siehe auch

[Globale Konstanten](../c-runtime-library/global-constants.md)