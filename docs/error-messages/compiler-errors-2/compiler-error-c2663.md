---
title: Compilerfehler C2663 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2663
dev_langs:
- C++
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fed35dcce056eb3d2a660c154e94b8058563dba7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083690"
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