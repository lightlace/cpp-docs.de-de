---
title: Compilerwarnung (Stufe 4) C4937
ms.date: 11/04/2016
f1_keywords:
- C4937
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
ms.openlocfilehash: dd7a7f9ac3d0ce0798a88f753cb0ccb4addbd5bc
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988753"
---
# <a name="compiler-warning-level-4-c4937"></a>Compilerwarnung (Stufe 4) C4937

'Text1' und 'Text2' sind als Argumente für 'Direktive' nicht differenzierbar.

Aufgrund der Art und Weise, wie der Compiler Argumente zu Direktiven verarbeitet, können Namen, die für den Compiler eine Bedeutung haben, z. B. Schlüsselwörter mit mehreren Textdarstellungen (Varianten mit einfachem und doppeltem Unterstrich), nicht unterschieden werden.

Beispiele für solche Zeichen folgen sind __cdecl und \__forceinline.  Beachten Sie, dass unter „/Za“ nur die Varianten mit doppeltem Unterstrich aktiviert sind.

Im folgenden Beispiel wird C4937 generiert:

```cpp
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
