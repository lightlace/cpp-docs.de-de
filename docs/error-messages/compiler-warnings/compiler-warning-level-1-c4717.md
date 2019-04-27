---
title: Compilerwarnung (Stufe 1) C4717
ms.date: 11/04/2016
f1_keywords:
- C4717
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
ms.openlocfilehash: 0cf9aef8f68ca5972fd3d7886cd8061b88d043ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221140"
---
# <a name="compiler-warning-level-1-c4717"></a>Compilerwarnung (Stufe 1) C4717

"Function": rekursiv für alle Steuerelementpfade, die Funktion verursacht einen Stapelüberlauf zur Laufzeit

Jeder Pfad durch eine Funktion enthält einen Aufruf der Funktion. Da keine Möglichkeit, die die Funktion erst nach Aufrufen von sich selbst rekursiv beendet ist, wird die Funktion nie beendet werden.

Im folgende Beispiel wird die C4717 generiert:

```
// C4717.cpp
// compile with: /W1 /c
// C4717 expected
int func(int x) {
   if (x > 1)
      return func(x - 1); // recursive call
   else {
      int y = func(0) + 1; // recursive call
      return y;
   }
}

int main(){
   func(1);
}
```