---
title: Compilerfehler C3890 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3890
dev_langs:
- C++
helpviewer_keywords:
- C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e599150c1e8d62d751f9dca67cffc99fb079bd32
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104921"
---
# <a name="compiler-error-c3890"></a>Compilerfehler C3890

'Var': Sie können die Adresse eines literal-Datenmembers nicht übernehmen

Ein literal-Datenmember, die auf dem Heap der Garbage collection vorhanden ist.  Ein Objekt auf dem Heap der Garbage collection kann verschoben werden, damit das Übernehmen der Adresse nicht nützlich ist.

Im folgende Beispiel wird die C3890 generiert:

```
// C3890.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   int p = &Y1::staticConst;   // C3890
   int p2 = Y1::staticConst;   // OK
}
```