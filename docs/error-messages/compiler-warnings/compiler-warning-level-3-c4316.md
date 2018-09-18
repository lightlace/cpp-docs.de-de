---
title: Compilerwarnung (Stufe 3) C4316 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4316
dev_langs:
- C++
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4170481b95cca0d43aa03c776009a5030194a4c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032925"
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