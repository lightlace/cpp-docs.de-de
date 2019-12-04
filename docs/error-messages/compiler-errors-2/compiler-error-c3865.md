---
title: Compilerfehler C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 960c795fe934433e4e3cf79e4c01c49d00205b9b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761490"
---
# <a name="compiler-error-c3865"></a>Compilerfehler C3865

' calling_convention ': kann nur für Native Member-Funktionen verwendet werden.

Eine Aufruf Konvention wurde für eine Funktion verwendet, bei der es sich entweder um eine globale Funktion oder um eine verwaltete Member-Funktion handelte. Die Aufruf Konvention kann nur in einer nativen (nicht verwalteten) Member-Funktion verwendet werden.

Weitere Informationen finden Sie unter [Aufrufen von Konventionen](../../cpp/calling-conventions.md).

Im folgenden Beispiel wird C3865 generiert:

```cpp
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```
