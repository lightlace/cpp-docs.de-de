---
title: Compilerfehler C2062
ms.date: 11/04/2016
f1_keywords:
- C2062
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
ms.openlocfilehash: dcfac9629a90b82744f87ec105c30301b2102cdf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408744"
---
# <a name="compiler-error-c2062"></a>Compilerfehler C2062

Typ 'Typ' unerwartete

Der Compiler wurde einen Typnamen nicht erwartet werden.

Im folgende Beispiel wird die C2062 generiert:

```
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062 kann auch auftreten, wenn der Compiler nicht definierte Typen in der Parameterliste des Konstruktors findet. Findet der Compiler einen undefinierten Typ für die (falsch geschrieben?), wird es an der Konstruktor ist ein Ausdruck, und C2062. Um zu beheben, müssen verwenden Sie definierte Typen nur in einer Parameterliste für Konstruktor.