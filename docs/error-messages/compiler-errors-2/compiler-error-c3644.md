---
title: Compilerfehler C3644 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3644
dev_langs:
- C++
helpviewer_keywords:
- C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63e48b944bd5b828ece1110240c462584703ba73
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099485"
---
# <a name="compiler-error-c3644"></a>Compilerfehler C3644

'Funktion': die Funktion zum Generieren von verwalteten Codes kann nicht kompiliert werden.

Das Vorhandensein von Schlüsselwörtern in einer Funktion bewirkt, dass die Funktion in systemeigenem Code kompiliert werden.

Im folgende Beispiel wird die C3644 generiert:

```
// C3644.cpp
// compile with: /clr
// processor: x86

void __clrcall Func2(int i) {
   __asm {}   // C3644
}
```