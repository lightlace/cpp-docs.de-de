---
title: Barriere | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- barrier
dev_langs:
- C++
helpviewer_keywords:
- barrier OpenMP directive
ms.assetid: 5c73ad4f-c768-443a-8f9e-4fd8bc2253c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c220106d62bf65505c9c5b48085a9ee3e67fe0cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415030"
---
# <a name="barrier"></a>barrier

Synchronisiert alle Threads in einem Team. Alle Threads anhalten die Barriere, bis alle Threads die Barriere ausführen.

## <a name="syntax"></a>Syntax

```
#pragma omp barrier
```

## <a name="remarks"></a>Hinweise

Die `barrier` -Anweisung unterstützt keine OpenMP-Klauseln.

Weitere Informationen finden Sie unter [2.6.3 Barrier-Direktive](../../../parallel/openmp/2-6-3-barrier-directive.md).

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung `barrier`, finden Sie unter [master](../../../parallel/openmp/reference/master.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen](../../../parallel/openmp/reference/openmp-directives.md)