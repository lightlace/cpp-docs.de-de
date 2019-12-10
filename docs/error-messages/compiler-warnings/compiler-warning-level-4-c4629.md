---
title: Compilerwarnung (Stufe 4) C4629
ms.date: 11/04/2016
f1_keywords:
- C4629
helpviewer_keywords:
- C4629
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
ms.openlocfilehash: 4aaaf3d592398981c1266a0ffbc1625da7d906af
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990620"
---
# <a name="compiler-warning-level-4-c4629"></a>Compilerwarnung (Stufe 4) C4629

"Digraph" wurde verwendet, Zeichensequenz "Digraph" wurde als Token "Zeichen" interpretiert (Fügen Sie zwischen den beiden Zeichen ein Leerzeichen ein, wenn Sie etwas anderes beabsichtigt haben)

Bei [/Za](../../build/reference/za-ze-disable-language-extensions.md)gibt der Compiler eine Warnung aus, wenn er einen Digraph erkennt.

Im folgenden Beispiel wird C4629 generiert.

```cpp
// C4629.cpp
// compile with: /Za /W4
int main()
<%   // C4629 <% digraph for {
}
```
