---
title: Compilerwarnung (Stufe 1) C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: f54f29fcbc6fb71033bc6d1d87c7ddb31622ee40
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051253"
---
# <a name="compiler-warning-level-1-c4822"></a>Compilerwarnung (Stufe 1) C4822

"Member": Lokale Klassenmemberfunktion enthält keinen Text.

Eine lokale Klassenmemberfunktion wurde deklariert, aber nicht in der Klasse definiert. Um eine lokale Klassenmemberfunktion verwenden zu können, müssen Sie sie in der Klasse definieren. Sie können Sie nicht in der Klasse deklarieren und außerhalb der Klasse definieren.

Jede Definition außerhalb der Klasse für eine lokale Klassenmemberfunktion erzeugt einen Fehler.

Im folgenden Beispiel wird C4822 generiert.

```cpp
// C4822.cpp
// compile with: /W1
int main() {
   struct C {
      void func1(int);   // C4822
      // try the following line instead
      // void func1(int){}
  };
}
```