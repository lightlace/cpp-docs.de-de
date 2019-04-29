---
title: Compilerwarnung (Stufe 3) C4316
ms.date: 11/04/2016
f1_keywords:
- C4316
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
ms.openlocfilehash: 5f895a231c8b32d76e4ccd3c15ffae5717d8017f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402046"
---
# <a name="compiler-warning-level-3-c4316"></a>Compilerwarnung (Stufe 3) C4316

Das Objekt, das auf dem Heap zugewiesen wird, ist für diesen Typ möglicherweise nicht ausgerichtet.

Ein über-ausgerichtetes Objekt, das mithilfe von `operator new` zugeordnet wird, hat möglicherweise nicht die angegebene Ausrichtung. Außer Kraft setzen [new-Operator](../../c-runtime-library/operator-new-crt.md) und [Delete-Operator](../../c-runtime-library/operator-delete-crt.md) für über-ausgerichtete Typen, damit diese die ausgerichteten speicherbelegungsroutinen verwenden – z. B. [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) und [_aligned_free](../../c-runtime-library/reference/aligned-free.md). Im folgende Beispiel wird die C4316 generiert:

```cpp
// C4316.cpp
// Test: cl /W3 /c C4316.cpp

__declspec(align(32)) struct S {}; // C4324

int main() {
    new S; // C4316
}
```