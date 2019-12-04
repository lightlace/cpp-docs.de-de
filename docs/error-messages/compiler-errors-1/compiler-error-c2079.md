---
title: Compilerfehler C2079
ms.date: 11/04/2016
f1_keywords:
- C2079
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
ms.openlocfilehash: ea158d8dada013f6b90d0fbe1e7502665c1c24da
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757721"
---
# <a name="compiler-error-c2079"></a>Compilerfehler C2079

' Identifier ' verwendet nicht definierte Klasse/Struktur/Union ' Name '

Der angegebene Bezeichner ist eine nicht definierte Klasse, Struktur oder Union.

Dieser Fehler kann dadurch verursacht werden, dass eine anonyme Union initialisiert wird.

Im folgenden Beispiel wird C2079 generiert:

```cpp
// C2079.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   std::ifstream g;   // C2079
}
```

Mögliche Lösung:

```cpp
// C2079b.cpp
// compile with: /EHsc
#include <fstream>
int main( ) {
   std::ifstream g;
}
```

C2079 kann auch auftreten, wenn Sie versuchen, ein Objekt im Stapel eines Typs zu deklarieren, dessen vorwärts Deklaration nur im Gültigkeitsbereich liegt.

```cpp
// C2079c.cpp
class A;

class B {
   A a;   // C2079
};

class A {};
```

Mögliche Lösung:

```cpp
// C2079d.cpp
// compile with: /c
class A;
class C {};

class B {
   A * a;
   C c;
};

class A {};
```
