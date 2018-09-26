---
title: _CRT_DISABLE_PERFCRIT_LOCKS | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
dev_langs:
- C++
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd01cbddac128e2369971d07320ff95986d822f9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053894"
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