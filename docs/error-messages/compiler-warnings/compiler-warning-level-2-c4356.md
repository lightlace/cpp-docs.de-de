---
title: Compilerwarnung (Stufe 2) C4356 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4356
dev_langs:
- C++
helpviewer_keywords:
- C4356
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 463ecd1bdd41c07baab0cf90c978411e51b4be04
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118725"
---
# <a name="compiler-warning-level-2-c4356"></a>Compilerwarnung (Stufe 2) C4356

'Member': statische Datenmember kann nicht über eine abgeleitete Klasse initialisiert werden

Die Initialisierung des ein statischer Datenmember wurde nicht ordnungsgemäß formatiert. Der Compiler akzeptiert die Initialisierung. Um die Warnung zu vermeiden, initialisieren Sie das Element über die Basisklasse aus.

Verwenden der [Warnung](../../preprocessor/warning.md) Pragma, um diese Warnung unterdrücken.

Im folgende Beispiel wird die C4356 generiert:

```
// C4356.cpp
// compile with: /W2 /EHsc
#include <iostream>

template <class T>
class C {
   static int n;
};

class D : C<int> {};

int D::n = 0; // C4356
// try the following line instead
// int C<int>::n = 0;

class A {
public:
   static int n;
};

class B : public A {};

int B::n = 10;   // C4356
// try the following line instead
// int A::n = 99;

int main() {
   using namespace std;
   cout << B::n << endl;
}
```