---
title: Compilerfehler C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: f07b63202d8f171dfb69f4bb294b392152b9290b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756031"
---
# <a name="compiler-error-c2663"></a>Compilerfehler C2663

"Funktion": Zahlen Überladungen weisen keine zulässigen Konvertierungen für den this-Zeiger auf.

Der Compiler konnte `this` nicht in eine der überladenen Versionen der Member-Funktion konvertieren.

Dieser Fehler kann verursacht werden, wenn eine nicht-`const` Member-Funktion für ein `const`-Objekt aufgerufen wird.  Mögliche Lösungen:

1. Entfernen Sie die `const` aus der Objekt Deklaration.

1. Fügen Sie einer der Element Funktions Überladungen `const` hinzu.

Im folgenden Beispiel wird C2663 generiert:

```cpp
// C2663.cpp
struct C {
   void f() volatile {}
   void f() {}
};

struct D {
   void f() volatile;
   void f() const {}
};

const C *pcc;
const D *pcd;

int main() {
   pcc->f();    // C2663
   pcd->f();    // OK
}
```
