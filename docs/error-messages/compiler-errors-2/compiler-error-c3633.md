---
title: Compilerfehler C3633
ms.date: 11/04/2016
f1_keywords:
- C3633
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
ms.openlocfilehash: 5f44c94cbb3c945406835816d8fc6ed7c39480eb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742625"
---
# <a name="compiler-error-c3633"></a>Compilerfehler C3633

"Member" kann nicht als Member des verwalteten Typs "Typ" definiert werden.

CLR-Verweisklassendatenmember dürfen nicht von einem C++ nicht-POD-Typ sein.  Sie können einen nativen POD-Typ nur in einem CLR-Typ instanziieren.  Ein POD-Typ kann z. b. keinen Kopierkonstruktor oder Zuweisungs Operator enthalten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3633 generiert.

```cpp
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```
