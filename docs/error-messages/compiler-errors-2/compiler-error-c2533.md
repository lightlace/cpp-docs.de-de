---
title: Compilerfehler C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: b111448e7e9d8260a5101d05996a670013936894
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746408"
---
# <a name="compiler-error-c2533"></a>Compilerfehler C2533

„Bezeichner“: Rückgabetyp für Konstruktoren nicht zulässig

Ein Konstruktor kann keinen Rückgabetyp haben (auch keinen `void`-Rückgabetyp).

Eine häufige Ursache für diesen Fehler ist ein fehlendes Semikolon zwischen dem Ende einer Klassendefinition und der ersten Konstruktorimplementierung. Der Compiler erkennt die Klasse als Definition des Rückgabetyps für die Konstruktorfunktion und generiert „C2533“.

Im folgenden Beispiel wird C2533 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```
