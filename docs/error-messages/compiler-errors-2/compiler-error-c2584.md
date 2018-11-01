---
title: Compilerfehler C2584
ms.date: 11/04/2016
f1_keywords:
- C2584
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
ms.openlocfilehash: b61ad65555b5d5232468206f6170223c5f160a34
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556688"
---
# <a name="compiler-error-c2584"></a>Compilerfehler C2584

'Klasse': direkte Basisklasse "Basis2" kann nicht zugegriffen werden; bereits Basisklasse von "Basis1"

`Class` bereits direkt abgeleitet `Base1`. `Base2` auch abgeleitet `Base1`. `Class` keine Ableitung vom `Base2` , da dieser Wert bedeuten würde (indirekt) erben `Base1` in diesem Fall ist das nicht zulässig, da `Base1` ist bereits eine direkte Basisklasse.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2584 generiert.

```
// C2584.cpp
// compile with: /c
struct A1 {
   virtual int MyFunction();
};

struct A2 {
    virtual int MyFunction();
};

struct B1: public virtual A1, virtual A2 {
    virtual int MyFunction();
};

struct B2: public virtual A2, virtual A1 {
    virtual int MyFunction();
};

struct C: virtual B1, B2 {
    virtual int MyFunction();
};

struct Z : virtual B2, virtual C {   // C2584
// try the following line insted
// struct Z : virtual C {
    virtual int MyFunction();
};
```