---
title: Compilerfehler C3634
ms.date: 11/04/2016
f1_keywords:
- C3634
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
ms.openlocfilehash: 2acd76fee5e7ca309991e639044a45ea83ed112b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385666"
---
# <a name="compiler-error-c3634"></a>Compilerfehler C3634

'Funktion': eine abstrakte Methode einer verwalteten oder WinRTclass kann nicht definiert werden.

Eine abstrakte Methode kann in einer verwalteten oder WinRT-Klasse deklariert aber nicht definiert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3634 generiert:

```
// C3634.cpp
// compile with: /clr
ref class C {
   virtual void f() = 0;
};

void C::f() {   // C3634 - don't define managed class' pure virtual method
}
```
