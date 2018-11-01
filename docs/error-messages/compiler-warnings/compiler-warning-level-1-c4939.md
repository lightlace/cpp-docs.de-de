---
title: Compilerwarnung (Stufe 1) C4939
ms.date: 11/04/2016
f1_keywords:
- C4939
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
ms.openlocfilehash: 00526b3dae5035fe96ec1abb50bbdd056ceecfaf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538532"
---
# <a name="compiler-warning-level-1-c4939"></a>Compilerwarnung (Stufe 1) C4939

\#Pragma-Vtordisp ist veraltet und wird in einer zukünftigen Version von Visual C++ entfernt

Das [vtordisp](../../preprocessor/vtordisp.md) -Pragma wird in einer der nächsten Versionen von Visual C++ entfernt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4939 generiert.

```
// C4939.cpp
// compile with: /c /W1
#pragma vtordisp(off)   // C4939
```