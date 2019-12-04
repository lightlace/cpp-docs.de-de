---
title: Compilerfehler C2073
ms.date: 11/04/2016
f1_keywords:
- C2073
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
ms.openlocfilehash: 545b2b24d3bfe5a36c5554dfa898d17b05067c3d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757734"
---
# <a name="compiler-error-c2073"></a>Compilerfehler C2073

"Bezeichner": Elemente eines teilweise initialisierten Arrays müssen einen Standardkonstruktor aufweisen.

Für ein Array von benutzerdefinierten Typen oder Konstanten wurden zu wenige Initialisierer angegeben. Wenn für einen Arraymember kein expliziter Initialisierer und der entsprechende Konstruktor angegeben sind, muss ein Standardkonstruktor angegeben werden.

Im folgenden Beispiel wird C2073 generiert:

```cpp
// C2073.cpp
class A {
public:
   A( int );   // constructor for ints only
};
A a[3] = { A(1), A(2) };   // C2073, no default constructor
```

```cpp
// C2073b.cpp
// compile with: /c
class B {
public:
   B();   // default constructor declared
   B( int );
};
B b[3] = { B(1), B(2) };   // OK
```
