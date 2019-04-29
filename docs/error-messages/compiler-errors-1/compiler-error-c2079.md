---
title: Compilerfehler C2079
ms.date: 11/04/2016
f1_keywords:
- C2079
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
ms.openlocfilehash: 68435610680e3b21415a1d9439a8133fd1e2557f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391958"
---
# <a name="compiler-error-c2079"></a>Compilerfehler C2079

'Bezeichner' wird nicht definierte Klasse/Struktur/Union "Name" verwendet.

Der angegebene Bezeichner ist eine nicht definierte Klasse, Struktur oder Union.

Dieser Fehler kann verursacht werden, durch die Initialisierung einer anonymen Union.

Im folgende Beispiel wird die C2079 generiert:

```
// C2079.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   std::ifstream g;   // C2079
}
```

Mögliche Lösung:

```
// C2079b.cpp
// compile with: /EHsc
#include <fstream>
int main( ) {
   std::ifstream g;
}
```

C2079 kann auch auftreten, wenn Sie versuchen, ein Objekt auf dem Stapel eines Typs deklarieren, deren Vorwärtsdeklaration nur im Gültigkeitsbereich befindet.

```
// C2079c.cpp
class A;

class B {
   A a;   // C2079
};

class A {};
```

Mögliche Lösung:

```
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