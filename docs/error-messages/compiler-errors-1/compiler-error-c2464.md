---
title: Compilerfehler C2464 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2464
dev_langs:
- C++
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff74085364d6638772ab2376aace93fea741056b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103140"
---
# <a name="compiler-error-c2464"></a>Compilerfehler C2464

'Bezeichner': kann nicht "new" verwenden, um die Zuordnung eines Verweises

Eine Referenz-ID zugeordnet war die `new` Operator. Verweise sind also nicht Memory-Objekte, `new` kann keinen Zeiger darauf zurückgeben. Verwenden Sie die standard-Variablendeklaration-Syntax, um einen Verweis zu deklarieren.

Im folgende Beispiel wird die C2464 generiert:

```
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```