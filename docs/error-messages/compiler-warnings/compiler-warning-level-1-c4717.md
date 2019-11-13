---
title: Compilerwarnung (Stufe 1) C4717
ms.date: 11/04/2016
f1_keywords:
- C4717
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
ms.openlocfilehash: 0bc95cc770914a1c02a7a40f9754415c2f013d63
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051344"
---
# <a name="compiler-warning-level-1-c4717"></a>Compilerwarnung (Stufe 1) C4717

"Function": rekursiv für alle Steuerelement Pfade, Funktion führt zu einem Lauf Zeit Stapelüberlauf

Jeder Pfad durch eine Funktion enthält einen aufzurufenden Befehl. Da es keine Möglichkeit gibt, die Funktion zu beenden, ohne sich zuerst selbst rekursiv aufrufen zu müssen, wird die Funktion nie beendet.

Im folgenden Beispiel wird C4717 generiert:

```cpp
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