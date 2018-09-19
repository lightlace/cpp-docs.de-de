---
title: Compilerwarnung (Stufe 1) C4939 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4939
dev_langs:
- C++
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e13cab2d5277cca0a1962b8ec254aaef10cfc98
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118764"
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