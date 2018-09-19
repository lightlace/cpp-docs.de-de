---
title: Compilerfehler C2698 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7ca3e7568640aabd2b7960d97ea94a11a1d5d59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118920"
---
# <a name="compiler-error-c2698"></a>Compilerfehler C2698

Die using-Deklaration für "Deklaration 1" kann nicht gleichzeitig vorhanden sein, mit der vorhandenen using-Deklaration für "Deklaration 2"

Nachdem Sie haben eine [using-Deklaration](../../cpp/using-declaration.md) für einen Datenmember, die jede Deklaration im gleichen Bereich mit dem gleichen Namen ist nicht zulässig, da nur Funktionen, die überladen werden können.

Im folgende Beispiel wird die C2698 generiert:

```
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