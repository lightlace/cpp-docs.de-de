---
title: Compilerwarnung (Stufe 1) C4319 | Microsoft Docs
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4319
dev_langs:
- C++
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1b5fe896ae7d8f43708b60ee4dda486ef08f428
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284744"
---
# <a name="compiler-warning-level-1-c4319"></a>Compilerwarnung (Stufe 1) C4319

> ' ~ ": Null erweitern"*Typ1*'to'*Typ2*"größerem

Das Ergebnis der **~** (bitweiser Komplementoperator) ist möglicherweise nicht signiert und anschließend mit 0 erweitert, wenn er in einen größeren Typ konvertiert wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel `~(a - 1)` als ein 32-Bit-unsigned long-Ausdruck ausgewertet und dann von 0 (null) Erweiterung zu 64 Bit konvertiert. Dies kann zu unerwarteten Vorgangsergebnisse führen.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
