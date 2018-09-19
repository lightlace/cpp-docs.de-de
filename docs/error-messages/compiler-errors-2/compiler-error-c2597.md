---
title: Compilerfehler C2597 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2597
dev_langs:
- C++
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9f8deb325ae54393518698263f3ca93ca88ca48
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114448"
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