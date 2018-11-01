---
title: Compilerfehler C2593
ms.date: 11/04/2016
f1_keywords:
- C2593
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
ms.openlocfilehash: c358553a36104b5c389076f5a5ce02f94f85e85a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667310"
---
# <a name="compiler-error-c2593"></a>Compilerfehler C2593

'Operator Bezeichner' ist mehrdeutig

Mehr als einen möglichen Operator ist für einen überladenen Operator definiert.

Dieser Fehler möglicherweise behoben werden, wenn Sie eine explizite Umwandlung auf eine oder mehrere Parameter verwenden.

Im folgende Beispiel wird die C2593 generiert:

```
// C2593.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};
void operator+( X, X );
void operator+( A, B );
D d;

int main() {
   d +  d;         // C2593, D has an A, B, and X
   (X)d + (X)d;    // OK, uses operator+( X, X )
}
```

Dieser Fehler kann verursacht werden, durch Serialisierung eine Gleitkommazahl Variable mit einem `CArchive` Objekt. Der Compiler identifiziert die `<<` Operator als mehrdeutig. Die C++ nur primitive Typen, `CArchive` können serialisieren, werden die Typen mit fester Größe `BYTE`, `WORD`, `DWORD`, und `LONG`. Alle Integer-Typen müssen in einem dieser Typen für die Serialisierung umgewandelt werden. Gleitkomma-Datentypen müssen archiviert werden, mithilfe der `CArchive::Write()` Member-Funktion.

Das folgende Beispiel zeigt, wie Sie eine Gleitkommavariable archivieren (`f`) Archiv `ar`:

```
ar.Write(&f, sizeof( float ));
```