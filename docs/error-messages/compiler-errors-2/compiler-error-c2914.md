---
title: Compilerfehler C2914
ms.date: 11/04/2016
f1_keywords:
- C2914
helpviewer_keywords:
- C2914
ms.assetid: fc6a0592-f53e-4f5a-88cb-780bbed4acf2
ms.openlocfilehash: 2500736f799032aea71173931139404b4406a16a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659583"
---
# <a name="compiler-error-c2914"></a>Compilerfehler C2914

'Bezeichner': Argument vom Typ kann nicht hergeleitet werden, da das Funktionsargument mehrdeutig ist.

Der Compiler ermitteln nicht, welche überladenen Funktionen für eine generische oder Vorlagenklasse-Argument verwenden sollen.

Im folgende Beispiel wird die C2914 generiert:

```
// C2914.cpp
// compile with: /c
void f(int);
void f(double);
template<class T> void g(void (*) (T));
void h() { g(f); }   // C2914
// try the following line instead
// void h() { g<int>(f); }
```

C2914 kann auch auftreten, wenn Generika verwendet werden.  Im folgende Beispiel wird die C2914 generiert:

```
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