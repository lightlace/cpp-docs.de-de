---
title: Compilerfehler C2974 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2974
dev_langs:
- C++
helpviewer_keywords:
- C2974
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 478639ee1eccf841361e8e7e880ac33669d69e1e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100479"
---
# <a name="compiler-error-c2974"></a>Compilerfehler C2974

Ungültiger Typ das Argument "Zahl", erwartet wurde der Typ

Das generische oder Vorlagenklasse Argument entspricht nicht der generische oder Vorlagendeklaration. Ein Typ sollte in spitzen Klammern angezeigt werden. Überprüfen Sie die generische oder Vorlagenklasse Definition so, dass die richtigen Typen zu ermitteln.

Im folgende Beispiel wird die C2974 generiert:

```
// C2974.cpp
// C2974 expected
template <class T>
struct TC {};

template <typename T>
void tf(T){}

int main() {
   // Delete the following 2 lines to resolve
   TC<1>* tc;
   tf<"abc">("abc");

   TC<int>* tc;
   tf<const char *>("abc");
}
```

C2974 kann auch auftreten, wenn Generika verwendet werden:

```
// C2974b.cpp
// compile with: /clr
// C2974 expected
using namespace System;
generic <class T>
ref struct GCtype {};

generic <typename T>
void gf(T){}

int main() {
   // Delete the following 2 lines to resolve
   GCtype<"a">^ gc;
   gf<"a">("abc");

   // OK
   GCtype<int>^ gc;
   gf<String ^>("abc");
}
```