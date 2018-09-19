---
title: Compilerwarnung (Stufe 3) C4823 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c3a6f24a32267f221dbc37e242bae48c0056af5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044651"
---
# <a name="compiler-warning-level-3-c4823"></a>Compilerwarnung (Stufe 3) C4823

'Funktion': verwendet, die feste Zeigern, die Entladesemantik ist aber nicht aktiviert. Erwägen Sie die Verwendung von/EHa

Um ein Objekt auf dem verwalteten Heap verweist ein fester Zeiger deklariert, die in einem Blockbereich lösen zu können, wird der Compiler das Verhalten von Destruktoren für lokale Klassen, die "als", ob der feste Zeiger einen Destruktor enthält, der den Zeiger hebt simuliert. Um einen Aufruf von einem Destruktor nach dem Auslösen einer Ausnahme zu aktivieren, müssen Sie aktivieren Objekt entladen zu können, wozu können Sie [/EHsc](../../build/reference/eh-exception-handling-model.md).

Sie können auch manuell lösen das Objekt und die Warnung ignorieren.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4823 generiert.

```
// C4823.cpp
// compile with: /clr /W3 /EHa-
using namespace System;

ref struct G {
   int m;
};

void f(G ^ pG) {
   try {
      pin_ptr<int> p = &pG->m;
      // manually unpin, ignore warning
      // p = nullptr;
      throw gcnew Exception;
   }
   catch(Exception ^) {}
}   // C4823 warning

int main() {
   f( gcnew G );
}
```
