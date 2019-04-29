---
title: Compilerfehler C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 00cb13d1999b00dfcaa5a2bc7bfb3b8eb16af5f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386979"
---
# <a name="compiler-error-c2533"></a>Compilerfehler C2533

„Bezeichner“: Rückgabetyp für Konstruktoren nicht zulässig

Ein Konstruktor kann keinen Rückgabetyp haben (auch keinen `void`-Rückgabetyp).

Eine häufige Ursache für diesen Fehler ist ein fehlendes Semikolon zwischen dem Ende einer Klassendefinition und der ersten Konstruktorimplementierung. Der Compiler erkennt die Klasse als Definition des Rückgabetyps für die Konstruktorfunktion und generiert „C2533“.

Im folgenden Beispiel wird C2533 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```