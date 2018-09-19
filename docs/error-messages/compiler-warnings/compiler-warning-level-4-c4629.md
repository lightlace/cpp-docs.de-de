---
title: Compilerwarnung (Stufe 4) C4629 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4629
dev_langs:
- C++
helpviewer_keywords:
- C4629
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5f728d60a654a672002610d41aa4e387b4479e0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081317"
---
# <a name="compiler-warning-level-4-c4629"></a>Compilerwarnung (Stufe 4) C4629

"Digraph" wurde verwendet, Zeichensequenz "Digraph" wurde als Token "Zeichen" interpretiert (Fügen Sie zwischen den beiden Zeichen ein Leerzeichen ein, wenn Sie etwas anderes beabsichtigt haben)

Bei [/Za](../../build/reference/za-ze-disable-language-extensions.md)gibt der Compiler eine Warnung aus, wenn er einen Digraph erkennt.

Im folgenden Beispiel wird C4629 generiert.

```
// C4629.cpp
// compile with: /Za /W4
int main()
<%   // C4629 <% digraph for {
}
```