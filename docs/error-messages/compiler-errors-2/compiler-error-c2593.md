---
title: Compilerfehler C2593
ms.date: 11/04/2016
f1_keywords:
- C2593
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
ms.openlocfilehash: 2a385e35376ddce528678980705595bfb98aca95
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759346"
---
# <a name="compiler-error-c2593"></a>Compilerfehler C2593

"Operator Identifier" ist mehrdeutig

Für einen überladenen Operator ist mehr als ein möglicher Operator definiert.

Dieser Fehler kann korrigiert werden, wenn Sie eine explizite Umwandlung für einen oder mehrere tatsächliche Parameter verwenden.

Im folgenden Beispiel wird C2593 generiert:

```cpp
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

Dieser Fehler kann dadurch verursacht werden, dass eine Gleit Komma Variable mithilfe eines `CArchive`-Objekts serialisiert wird. Der Compiler identifiziert den `<<` Operator als mehrdeutig. Die einzigen primitiven C++ Typen, die `CArchive` serialisieren können, sind die Typen mit fester Größe `BYTE`, `WORD`, `DWORD`und `LONG`. Alle ganzzahligen Typen müssen für die Serialisierung in einen dieser Typen umgewandelt werden. Gleit Komma Typen müssen mithilfe der `CArchive::Write()` Member-Funktion archiviert werden.

Im folgenden Beispiel wird gezeigt, wie eine Gleit Komma Variable (`f`) archiviert wird, um `ar`zu archivieren:

```
ar.Write(&f, sizeof( float ));
```
