---
title: Compilerfehler C2062
ms.date: 11/04/2016
f1_keywords:
- C2062
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
ms.openlocfilehash: a709a540b24756a7e08f98552c5888a55c3ea601
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735969"
---
# <a name="compiler-error-c2062"></a>Compilerfehler C2062

der Typ "Typ" ist unerwartet.

Der Compiler hat keinen Typnamen erwartet.

Im folgenden Beispiel wird C2062 generiert:

```cpp
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062 kann auch auftreten, wenn der Compiler nicht definierte Typen in der Parameterliste eines Konstruktors behandelt. Wenn der Compiler auf einen nicht definierten Typ (falsch geschriebener Typ) stößt, wird davon ausgegangen, dass der Konstruktor ein Ausdruck ist und C2062 ausgibt. Um aufzulösen, verwenden Sie nur definierte Typen in einer konstruktorparameterliste.
