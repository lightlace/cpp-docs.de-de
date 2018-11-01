---
title: Compilerwarnung (Stufe 1) C4074
ms.date: 11/04/2016
f1_keywords:
- C4074
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
ms.openlocfilehash: d9b0259e95198396d8c34ca43781045248e22ad9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665566"
---
# <a name="compiler-warning-level-1-c4074"></a>Compilerwarnung (Stufe 1) C4074

Fügen Sie in den Compiler reservierten Initialisierungsbereich Initialisierer

Die Compiler-Initialisierungsbereich, die von angegeben wird [#pragma Init_seg](../../preprocessor/init-seg.md), ist durch Microsoft reserviert. Code in diesem Bereich möglicherweise vor der Initialisierung der C-Laufzeitbibliothek ausgeführt werden.

Im folgende Beispiel wird die C4074 generiert:

```
// C4074.cpp
// compile with: /W1
#pragma init_seg( compiler )   // C4074

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```