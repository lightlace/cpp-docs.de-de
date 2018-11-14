---
title: Compilerfehler C2797
ms.date: 11/04/2016
f1_keywords:
- C2797
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
ms.openlocfilehash: 04a7b2b1d33ab7efa77563406ab3c12831cf80fc
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518306"
---
# <a name="compiler-error-c2797"></a>Compilerfehler C2797

(Veraltet) Listeninitialisierung in Memberinitialisierer oder nicht statische datenmemberinitialisierer ist nicht implementiert.

Diese Warnung ist in Visual Studio 2015 veraltet. In Visual Studio 2013 und früheren Versionen implementiert nicht Listen-Initialisierung innerhalb einer Memberinitialisiererliste oder einem nicht statischen datenmemberinitialisierer entweder Visual C++-Compiler. Vor dem Visual Studio 2013 Update 3 wurde dies im Hintergrund in einen Funktionsaufruf konvertiert, der zur Generierung von ungültigem Code führen könnte. Visual Studio 2013 Update 3 meldet dies als Fehler.

In diesem Beispiel wird C2797 generiert:

```
#include <vector>
struct S {
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'

    std::vector<int> v1;
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'
};
```

In diesem Beispiel wird auch die C2797:

```
struct S1 {
    int i;
};

struct S2 {
    S2() : s1{0} {} // C2797, VS2013 RTM interprets as S2() : s1(0) {} causing C2664
    S1 s1;
    S1 s2{0}; // C2797, VS2013 RTM interprets as S1 s2 = S1(0); causing C2664
};
```

Um dieses Problem zu beheben, können Sie die explizite Konstruktion von inneren Listen verwendn. Beispiel:

```
#include <vector>
typedef std::vector<int> Vector;
struct S {
    S() : v1(Vector{1}) {}

    Vector v1;
    Vector v2 = Vector{1, 2};
};
```

Wenn Sie keine Listen-Initialisierung erfordern:

```
struct S {
    S() : s1("") {}

    std::string s1;
    std::string s2 = std::string("");
};
```

(Der Compiler in Visual Studio 2013 Fall vor dem Visual Studio 2013 Update 3 hat dies nur implizit ausgeführt.)