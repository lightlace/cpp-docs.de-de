---
title: Compilerfehler C2797 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2797
dev_langs:
- C++
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 701ec194c968b9f1d17269573b33e78d69fbb256
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035369"
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