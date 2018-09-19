---
title: Compilerwarnung (Stufe 1) C4103 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4103
dev_langs:
- C++
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1942acc2d9c5c274806e06127f9f98d4bfcb5077
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085536"
---
# <a name="compiler-warning-level-1-c4103"></a>Compilerwarnung (Stufe 1) C4103

'Dateiname': Ausrichtung wurde nach dem einschließen des Headers, möglicherweise aufgrund fehlender #pragma pack(pop)

Packen von Metriken, wirkt sich auf das Layout der Klassen aus, und häufig, wenn Änderungen in Headerdateien zu packen, sein können.

Verwenden Sie #pragma [Pack](../../preprocessor/pack.md)(pop) vor dem Beenden der Headerdatei, um diese Warnung zu beheben.

Im folgende Beispiel wird die C4103 generiert:

```
// C4103.h
#pragma pack(push, 4)

// defintions and declarations

// uncomment the following line to resolve
// #pragma pack(pop)
```

und anschließend

```
// C4103.cpp
// compile with: /LD /W1
#include "c4103.h"   // C4103
```