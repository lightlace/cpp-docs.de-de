---
title: Compilerwarnung (Stufe 1) C4810
ms.date: 11/04/2016
f1_keywords:
- C4810
helpviewer_keywords:
- C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
ms.openlocfilehash: b1f62b744547dc91923b397f3715c09659433a05
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052333"
---
# <a name="compiler-warning-level-1-c4810"></a>Compilerwarnung (Stufe 1) C4810

Wert von pragma pack(show) == n

Diese Warnung wird ausgegeben, wenn Sie die **show** -Option des [pack](../../preprocessor/pack.md) -Pragmas verwenden. *n* ist der aktuelle pack-Wert.

Der folgende Code zeigt z. B. die Funktionsweise der C4810-Warnung mit dem pack-Pragma:

```cpp
// C4810.cpp
// compile with: /W1 /LD
// C4810 expected
#pragma pack(show)
#pragma pack(4)
#pragma pack(show)
```