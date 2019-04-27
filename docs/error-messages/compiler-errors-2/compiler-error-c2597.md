---
title: Compilerfehler C2597
ms.date: 11/04/2016
f1_keywords:
- C2597
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
ms.openlocfilehash: b7bdd10ebd70eb61746690958532854dd98c6429
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228589"
---
# <a name="compiler-error-c2597"></a>Compilerfehler C2597

Ungültiger Verweis auf nicht statisches Member 'identifier'

Mögliche Ursachen:

1. Ein nicht statisches Member wird in einer statischen Memberfunktion angegeben. Für den Zugriff auf das nicht statische Member müssen Sie eine lokale Instanz der Klasse übergeben oder erstellen und einen Memberzugriffsoperator (`.` oder `->`) verwenden.

1. Der angegebene Bezeichner ist kein Member der Klasse, Struktur oder Union. Prüfen Sie die Schreibweise des Bezeichners.

1. Ein Memberzugriffsoperator bezieht sich auf eine Nicht-Memberfunktion.

1. Im folgenden Beispiel wird C2597 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2597.cpp
// compile with: /c
struct s1 {
   static void func();
   static void func2(s1&);
   int i;
};

void s1::func() {
   i = 1;    // C2597 - static function can't access non-static data member
}

// OK - fix by passing an instance of s1
void s1::func2(s1& a) {
   a.i = 1;
}
```