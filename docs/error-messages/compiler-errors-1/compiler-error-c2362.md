---
title: Compilerfehler C2362
ms.date: 11/04/2016
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: 17656b2a48a3680a9269d3ca300fd4188eda6b84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661109"
---
# <a name="compiler-error-c2362"></a>Compilerfehler C2362

Initialisierung von "Bezeichner" durch "Goto Label" übersprungen

Beim Kompilieren mit [/Za](../../build/reference/za-ze-disable-language-extensions.md), Springen zur Bezeichnung verhindert, dass den Bezeichner initialisiert wird.

Sie können nicht hinter einer Deklaration mit einem Initialisierer springen, es sei denn, die Deklaration in einem Block eingeschlossen ist, die nicht eingegeben wird, oder die Variable wurde bereits initialisiert.

Im folgenden Beispiel wird C2326 generiert:

```
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

Mögliche Lösung:

```
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```