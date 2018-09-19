---
title: Compilerfehler C3181 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3181
dev_langs:
- C++
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 599fe0afe4bdcdc7b1e2025859d11a38618b1349
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097340"
---
# <a name="compiler-error-c3181"></a>Compilerfehler C3181

'Typ': Ungültiger Operand für den Operator

Ein ungültiger Parameter wurde übergeben, um die [Typeid](../../windows/typeid-cpp-component-extensions.md) Operator. Der Parameter muss es sich um einen verwalteten Typ sein.

Beachten Sie, dass der Compiler Aliase für systemeigene Typen verwendet werden, die Typen in der common Language Runtime zugeordnet.

Im folgende Beispiel wird die C3181 generiert:

```
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```
