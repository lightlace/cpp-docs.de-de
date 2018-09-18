---
title: Compilerfehler C2062 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2062
dev_langs:
- C++
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbda0894b25e09681207d6447bb40727d490fc02
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072243"
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