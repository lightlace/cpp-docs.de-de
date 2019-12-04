---
title: Compilerfehler C2914
ms.date: 11/04/2016
f1_keywords:
- C2914
helpviewer_keywords:
- C2914
ms.assetid: fc6a0592-f53e-4f5a-88cb-780bbed4acf2
ms.openlocfilehash: bed9e31d7d1de069ee708f8f482d26b37bc16833
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761057"
---
# <a name="compiler-error-c2914"></a>Compilerfehler C2914

' Identifier ': Typargument kann nicht abgeleitet werden, da das Funktions Argument mehrdeutig ist

Der Compiler kann nicht bestimmen, welche überladenen Funktionen für ein generisches oder Vorlagen Argument verwendet werden sollen.

Im folgenden Beispiel wird C2914 generiert:

```cpp
// C2914.cpp
// compile with: /c
void f(int);
void f(double);
template<class T> void g(void (*) (T));
void h() { g(f); }   // C2914
// try the following line instead
// void h() { g<int>(f); }
```

C2914 kann auch auftreten, wenn Generika verwendet werden.  Im folgenden Beispiel wird C2914 generiert:

```cpp
// C2914b.cpp
// compile with: /clr /c
void f(int);
void f(double);

template<class T>
void gf(void (*) (T));

void h() { gf(f);}   // C2914
// try the following line instead
void h() { gf<int>(f); }
```
