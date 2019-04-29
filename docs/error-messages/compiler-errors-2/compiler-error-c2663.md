---
title: Compilerfehler C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: d74326e49edd980896276e2c6e67526d8d769cb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360293"
---
# <a name="compiler-error-c2663"></a>Compilerfehler C2663

'Funktion': Anzahl Überladung(en) gibt es keine zulässige Konvertierung für "this"-Zeiger

Der Compiler konnte nicht konvertiert werden `this` auf eine der überladenen Versionen der Memberfunktion.

Dieser Fehler kann verursacht werden, durch den Aufruf einer nicht -`const` Member-Funktion auf einem `const` Objekt.  Mögliche Lösungen:

1. Entfernen Sie die `const` aus der Objektdeklaration.

1. Hinzufügen `const` auf eine der Überladungen der Member-Funktion.

Im folgende Beispiel wird die C2663 generiert:

```
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