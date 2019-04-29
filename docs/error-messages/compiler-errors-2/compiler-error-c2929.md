---
title: Compilerfehler C2929
ms.date: 11/04/2016
f1_keywords:
- C2929
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
ms.openlocfilehash: fe2a56f7722c70c11e980fb6ee59230ffd056c5f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385718"
---
# <a name="compiler-error-c2929"></a>Compilerfehler C2929

"Bezeichner": Explizite Instanziierung; Instanziierung eines Elements einer Vorlagenklasse kann nicht explizit erzwungen und unterdrückt werden

Sie können einen Bezeichner nicht explizit instanziieren und gleichzeitig verhindern, dass er instanziiert wird.

Im folgenden Beispiel wird C2929 generiert:

```
// C2929.cpp
// compile with: /c
template<typename T>
class A {
public:
   A() {}
};

template A<int>::A();

extern template A<int>::A();   // C2929
```