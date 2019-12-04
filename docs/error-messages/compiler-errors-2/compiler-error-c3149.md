---
title: Compilerfehler C3149
ms.date: 11/04/2016
f1_keywords:
- C3149
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
ms.openlocfilehash: 263eb03b7a9f45458f8d8b586adc6f1cfc5805be
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745979"
---
# <a name="compiler-error-c3149"></a>Compilerfehler C3149

"Typ": dieser Typ kann hier ohne "char" der obersten Ebene nicht verwendet werden.

Eine Deklaration wurde nicht ordnungsgemäß angegeben.

Beispielsweise haben Sie möglicherweise einen CLR-Typ im globalen Gültigkeitsbereich definiert und versucht, eine Variable des Typs als Teil der Definition zu erstellen. Da globale Variablen von CLR-Typen nicht zulässig sind, generiert der Compiler C3149.

Um diesen Fehler zu beheben, deklarieren Sie Variablen von CLR-Typen in einer Funktions-oder Typdefinition.

Im folgenden Beispiel wird C3149 generiert:

```cpp
// C3149.cpp
// compile with: /clr
using namespace System;
int main() {
   // declare an array of value types
   array< Int32 ^> IntArray;   // C3149
   array< Int32>^ IntArray2;   // OK
}
```

Im folgenden Beispiel wird C3149 generiert:

```cpp
// C3149b.cpp
// compile with: /clr /c
delegate int MyDelegate(const int, int);
void Test1(MyDelegate m) {}   // C3149
void Test2(MyDelegate ^ m) {}   // OK
```
