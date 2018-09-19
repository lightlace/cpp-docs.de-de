---
title: Compilerwarnung (Stufe 4) C4937 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4937
dev_langs:
- C++
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7bc6232458b357f41e859c58d4b6b77f78ef2a7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118296"
---
# <a name="compiler-warning-level-4-c4937"></a>Compilerwarnung (Stufe 4) C4937

'Text1' und 'Text2' sind als Argumente für 'Direktive' nicht differenzierbar.

Aufgrund der Art und Weise, wie der Compiler Argumente zu Direktiven verarbeitet, können Namen, die für den Compiler eine Bedeutung haben, z. B. Schlüsselwörter mit mehreren Textdarstellungen (Varianten mit einfachem und doppeltem Unterstrich), nicht unterschieden werden.

Beispiele solcher Zeichenfolgen sind __cdecl und \__forceinline.  Beachten Sie, dass unter „/Za“ nur die Varianten mit doppeltem Unterstrich aktiviert sind.

Im folgenden Beispiel wird C4937 generiert:

```
// C4937.cpp
// compile with: /openmp /W4
#include "omp.h"
int main() {
   #pragma omp critical ( __leave )   // C4937
   ;

   // OK
   #pragma omp critical ( leave )
   ;
}
```