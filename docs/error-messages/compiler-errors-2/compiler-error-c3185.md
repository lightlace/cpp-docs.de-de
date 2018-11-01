---
title: Compilerfehler C3185
ms.date: 11/04/2016
f1_keywords:
- C3185
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
ms.openlocfilehash: db448b462cd3a3f325c529e730e5c8f65e2b8f51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598808"
---
# <a name="compiler-error-c3185"></a>Compilerfehler C3185

"TypeId" verwendet für verwalteten oder WinRT-Typ "Typ"; verwenden Sie stattdessen "Operator".

Sie können nicht angewendet werden die [Typeid](../../cpp/typeid-operator.md) Operator, um einen verwalteten oder WinRT-Typ; verwenden Sie [Typeid](../../windows/typeid-cpp-component-extensions.md) stattdessen.

Im folgenden Beispiel wird C3185 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3185a.cpp
// compile with: /clr
ref class Base {};
ref class Derived : public Base {};

int main() {
   Derived ^ pd = gcnew Derived;
   Base ^pb = pd;
   const type_info & t1 = typeid(pb);   // C3185
   System::Type ^ MyType = Base::typeid;   // OK
};
```
