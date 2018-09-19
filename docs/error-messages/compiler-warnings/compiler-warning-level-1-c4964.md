---
title: Compilerwarnung (Stufe 1) C4964 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4964
dev_langs:
- C++
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f1644e4603bae36ec9d407294dea78a27e60539
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086667"
---
# <a name="compiler-warning-level-1-c4964"></a>Compilerwarnung (Stufe 1) C4964

Es wurden keine Optimierungsoptionen angegeben. Informationen zum Unternehmensprofil werden nicht gesammelt werden

["/ GL"](../../build/reference/gl-whole-program-optimization.md) und ["/ LTCG"](../../build/reference/ltcg-link-time-code-generation.md) angegeben wurden, jedoch keine Optimierungen angefordert wurden, sodass keine PGC-Dateien generiert werden und daher keine Profilgesteuerte Optimierungen werden.

Wenn Sie möchten die PGC-Dateien generiert werden, wenn Sie Ihre Anwendung ausführen, geben Sie eine der der [/o](../../build/reference/o-options-optimize-code.md) Compileroptionen.

Im folgende Beispiel wird die C4964 generiert:

```
// C4964.cpp
// compile with: /W1 /GL /link /ltcg:pgi
// C4964 expected
// Add /O2, for example, to the command line to resolve this warning.
int main() {
   int i;
}
```