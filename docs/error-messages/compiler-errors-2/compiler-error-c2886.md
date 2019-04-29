---
title: Compilerfehler C2886
ms.date: 11/04/2016
f1_keywords:
- C2886
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
ms.openlocfilehash: 2fa7450f03505501c2c4a45023dbb6a86937bb9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388812"
---
# <a name="compiler-error-c2886"></a>Compilerfehler C2886

'class:: Identifier': Symbol kann nicht in eine Member-using-Deklaration verwendet werden

Ein `using` Deklaration verwendet ein Symbol an, wie z. B. einen Namespacenamen an. Ein `using` Deklaration ist für das Deklarieren von Member der Basisklasse.

Im folgende Beispiel wird die C2886 generiert:

```
// C2886.cpp
// compile with: /c
namespace Z {
    int i;
}

class B {
protected:
    int i;
};

class D : public B {
    // Error: Z is a namespace
    using Z::i;   // C2886

    // OK: B is a base class
    using B::i;
};
```