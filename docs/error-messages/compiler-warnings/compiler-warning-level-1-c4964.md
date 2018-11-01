---
title: Compilerwarnung (Stufe 1) C4964
ms.date: 11/04/2016
f1_keywords:
- C4964
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
ms.openlocfilehash: 556c6e0963fc41d76cd123373cc4cd85edc66962
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492049"
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