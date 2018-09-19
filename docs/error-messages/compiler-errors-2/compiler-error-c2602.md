---
title: Compilerfehler C2602 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2602
dev_langs:
- C++
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22c4b2ec765259aa7797b49c003f1b2e2860226f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049526"
---
# <a name="compiler-error-c2602"></a>Compilerfehler C2602

'class:: Identifier' ist kein Member einer Basisklasse von "Klasse"

`Identifier` kann nicht zugegriffen werden, da es sich nicht um einen von einer Basisklasse geerbten Member ist.

Im folgende Beispiel wird die C2602 generiert:

```
// C2602.cpp
// compile with: /c
struct X {
   int x;
};
struct A {
   int a;
};
struct B : public A {
   X::x;   // C2602 B is not derived from X
   A::a;   // OK
};
```