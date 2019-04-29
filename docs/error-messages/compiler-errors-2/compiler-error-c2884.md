---
title: Compilerfehler C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: d920629dc0697d0f2fdd05ac5aca6118b89b88cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378855"
---
# <a name="compiler-error-c2884"></a>Compilerfehler C2884

'Name': von using-Deklaration steht in Konflikt mit lokaler Funktion "Function" eingeführt

Sie haben versucht, eine Funktion mehr als einmal definiert. Die erste Definition befindet es sich um eine lokale Definition. Die zweite besteht aus einem Namespace mit einem `using` Deklaration.

Im folgende Beispiel wird die C2884 generiert:

```
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```