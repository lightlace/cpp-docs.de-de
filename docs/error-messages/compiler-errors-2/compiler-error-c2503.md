---
title: Compilerfehler C2503
ms.date: 11/04/2016
f1_keywords:
- C2503
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
ms.openlocfilehash: 4cfe574f79eae2e45dc62315245a1b8b773d04df
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746902"
---
# <a name="compiler-error-c2503"></a>Compilerfehler C2503

"Class": Basisklassen dürfen keine Arrays der Größen NULL enthalten.

Eine Basisklasse oder Struktur enthält ein Array der Größen NULL. Ein Array in einer Klasse muss mindestens ein Element aufweisen.

Im folgenden Beispiel wird C2503 generiert:

```cpp
// C2503.cpp
// compile with: /c
class A {
   public:
   int array [];
};

class B : A {};    // C2503

class C {
public:
   int array [10];
};

class D : C {};
```
