---
title: Compilerfehler C2698
ms.date: 11/04/2016
f1_keywords:
- C2698
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
ms.openlocfilehash: 6129ff691f804b31fdb8cb487ac4609e4bca6ef2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755186"
---
# <a name="compiler-error-c2698"></a>Compilerfehler C2698

die using-Deklaration für ' Declaration 1 ' kann nicht zusammen mit der vorhandenen using-Deklaration für ' Declaration 2 ' vorhanden sein.

Sobald Sie über eine [using-Deklaration](../../cpp/using-declaration.md) für einen Datenmember verfügen, ist jede using-Deklaration im gleichen Bereich, in der derselbe Name verwendet wird, nicht zulässig, da nur Funktionen überladen werden können.

Im folgenden Beispiel wird C2698 generiert:

```cpp
// C2698.cpp
struct A {
   int x;
};

struct B {
   int x;
};

struct C : A, B {
   using A::x;
   using B::x;   // C2698
}
```
