---
title: Compilerfehler C2561 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2561
dev_langs:
- C++
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8611af23ab884a853fc751ae82c636753993495b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070703"
---
# <a name="compiler-error-c2561"></a>Compilerfehler C2561

'Bezeichner': Funktion muss einen Wert zurückgeben

Die Funktion wurde als Rückgabewert deklariert, aber enthält keine Definition der Funktion ein `return` Anweisung.

Dieser Fehler kann durch einen falschen Funktionsprototyp verursacht werden:

1. Wenn die Funktion keinen Wert zurückgibt, deklarieren Sie die Funktion mit Rückgabetyp ["void"](../../cpp/void-cpp.md).

1. Überprüfen Sie, dass alle mögliche Verzweigungen der Funktion einen Wert des Typs im Prototyp deklariert zurückgibt.

1. C++-Funktionen mit Inline-Assembly-Routinen, die den Rückgabewert in speichern die `AX` registrieren Sie sich möglicherweise eine return-Anweisung. Kopieren Sie den Wert in `AX` in eine temporäre Variable und die Variable aus der Funktion zurückgegeben.

Im folgende Beispiel wird die C2561 generiert:

```
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