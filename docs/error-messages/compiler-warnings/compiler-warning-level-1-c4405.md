---
title: Compilerwarnung (Stufe 1) C4405
ms.date: 11/04/2016
f1_keywords:
- C4405
helpviewer_keywords:
- C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
ms.openlocfilehash: 182f9ff061fd2a8ebe5ea0046545412fca5f646a
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965585"
---
# <a name="compiler-warning-level-1-c4405"></a>Compilerwarnung (Stufe 1) C4405

"Bezeichner": Bezeichner ist ein reserviertes Wort

Ein Wort, das für die Inlineassembly reserviert ist, wird als Variablenname verwendet. Dies kann zu unvorhersehbaren Ergebnissen führen. Um diese Warnung zu beheben, vermeiden Sie das Benennen von Variablen, die für die Inlineassembly reserviert sind. Im folgenden Beispiel wird C4405 generiert:

```cpp
// C4405.cpp
// compile with: /W1
// processor: x86
void func1() {
   int mov = 0, i = 0;
   _asm {
      mov mov, 0;   // C4405
      // instead, try ..
      // mov i, 0;
   }
}

int main() {
}
```