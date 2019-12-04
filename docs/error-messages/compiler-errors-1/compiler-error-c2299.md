---
title: Compilerfehler C2299
ms.date: 11/04/2016
f1_keywords:
- C2299
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
ms.openlocfilehash: 009a441ec610053176e79126d9f2663f29b26bc6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759047"
---
# <a name="compiler-error-c2299"></a>Compilerfehler C2299

"Function": Behavior Change: eine explizite Spezialisierung kann kein Kopierkonstruktor oder Kopier Zuweisungs Operator sein.

Dieser Fehler kann auch als Ergebnis einer compilerübereinstimmungs-Arbeit generiert werden, die für Visual Studio 2005 ausgeführt wurde: vorherige C++ Versionen von Visual ermöglichten explizite Spezialisierungen für einen Kopierkonstruktor oder einen Kopier Zuweisungs Operator.

Um C2299 aufzulösen, machen Sie den Kopierkonstruktor oder Zuweisungs Operator nicht in eine Vorlagen Funktion, sondern eine nicht Vorlagen Funktion, die einen Klassentyp annimmt. Jeder Code, der den Kopierkonstruktor oder Zuweisungs Operator durch explizites angeben der Vorlagen Argumente aufruft, muss die Vorlagen Argumente entfernen.

Im folgenden Beispiel wird C2299 generiert:

```cpp
// C2299.cpp
// compile with: /c
class C {
   template <class T>
   C (T t);

   template <> C (const C&);   // C2299
   C (const C&);   // OK
};
```
