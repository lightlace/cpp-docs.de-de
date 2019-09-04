---
title: Compilerfehler C2760
ms.date: 11/04/2016
f1_keywords:
- C2760
helpviewer_keywords:
- C2760
ms.assetid: 585757fd-d519-43f3-94e5-50316ac8b90b
ms.openlocfilehash: 5680de2fe0364d7cdc5e7ef017bd298423ea4c21
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273666"
---
# <a name="compiler-error-c2760"></a>Compilerfehler C2760

> Syntax Fehler: '*Name1*' ist nicht '*name2*' erwartet.

## <a name="remarks"></a>Hinweise

Es gibt mehrere Möglichkeiten, diesen Fehler zu verursachen. Normalerweise wird dies durch eine tokensequenz verursacht, von der der Compiler nicht Sinn macht.

## <a name="example"></a>Beispiel

In diesem Beispiel wird ein Umwandlungs Operator mit einem ungültigen Operator verwendet.

```cpp
// C2760.cpp
class B {};
class D : public B {};

void f(B* pb) {
    D* pd1 = static_cast<D*>(pb);
    D* pd2 = static_cast<D*>=(pb);  // C2760
    D* pd3 = static_cast<D*=(pb);   // C2760
}
```
