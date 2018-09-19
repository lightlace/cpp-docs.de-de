---
title: Compilerwarnung (Stufe 1) C4333 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4333
dev_langs:
- C++
helpviewer_keywords:
- C4333
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0813b39e607f5aee1a9a6f5e133216247d8573c8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074200"
---
# <a name="compiler-warning-level-1-c4333"></a>Compilerwarnung (Stufe 1) C4333

'Operator': rechtsverschiebung Betrag zu groß, Verlust von Daten

Ein Verschiebung nach rechts-Vorgang war zu groß.  Alle signifikanten Bits werden verschoben, und das Ergebnis ist immer 0 (null).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4333 generiert.

```
// C4333.cpp
// compile with: /c /W1
unsigned shift8 (unsigned char c) {
   return c >> 8;   // C4333

   // try the following line instead
   // return c >> 4;   // OK
}
```