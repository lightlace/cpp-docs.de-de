---
title: Compilerfehler C2079 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2079
dev_langs:
- C++
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ddea9a8651a62f7cbb857e1d53962142471c2cb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032177"
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