---
title: Compilerfehler C2561
ms.date: 11/04/2016
f1_keywords:
- C2561
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
ms.openlocfilehash: b4a14be9cd32c752e2ab889417494e80b935e31b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755563"
---
# <a name="compiler-error-c2561"></a>Compilerfehler C2561

"Bezeichner": die Funktion muss einen Wert zurückgeben.

Die Funktion wurde als Rückgabe eines Werts deklariert, aber die Funktionsdefinition enthält keine `return` Anweisung.

Dieser Fehler kann durch einen falschen Funktionsprototyp verursacht werden:

1. Wenn die Funktion keinen Wert zurückgibt, deklarieren Sie die Funktion mit dem Rückgabetyp [void](../../cpp/void-cpp.md).

1. Überprüfen Sie, ob alle möglichen Verzweigungen der Funktion einen Wert des im Prototyp deklarierten Typs zurückgeben.

1. C++Funktionen, die Inline-Assemblyroutinen enthalten, die den Rückgabewert im `AX` Register speichern, benötigen möglicherweise eine Return-Anweisung. Kopieren Sie den Wert in `AX` in eine temporäre Variable, und geben Sie diese Variable von der-Funktion zurück.

Im folgenden Beispiel wird C2561 generiert:

```cpp
// C2561.cpp
int Test(int x) {
   if (x) {
      return;   // C2561
      // try the following line instead
      // return 1;
   }
   return 0;
}

int main() {
   Test(1);
}
```
