---
title: Compilerfehler C2584
ms.date: 11/04/2016
f1_keywords:
- C2584
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
ms.openlocfilehash: 2c3b10ecd6808ccd864ecf877fe9f1d0e9f30a3a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748631"
---
# <a name="compiler-error-c2584"></a>Compilerfehler C2584

"Klasse": auf die direkte Basis "base2" kann nicht zugegriffen werden. ist bereits eine Basis von "base1".

`Class` bereits direkt von `Base1`abgeleitet. `Base2` wird auch von `Base1`abgeleitet. `Class` können nicht von `Base2` abgeleitet werden, da dies wiederum wiederum die Vererbung (indirekt) von `Base1` bedeuten würde, da `Base1` bereits eine direkte Basisklasse ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2584 generiert.

```cpp
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
