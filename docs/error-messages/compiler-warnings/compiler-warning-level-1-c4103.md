---
title: Compilerwarnung (Stufe 1) C4103
ms.date: 11/04/2016
f1_keywords:
- C4103
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
ms.openlocfilehash: 15d7403d461467e33b7e89957821a311179d33a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300284"
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