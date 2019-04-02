---
title: Compilerfehler C3185
ms.date: 11/04/2016
f1_keywords:
- C3185
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
ms.openlocfilehash: 45afe70b454f72dd8c9b8ce9771ce1f5aef6a10e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773189"
---
# <a name="compiler-error-c3185"></a>Compilerfehler C3185

"TypeId" verwendet für verwalteten oder WinRT-Typ "Typ"; verwenden Sie stattdessen "Operator".

Sie können nicht angewendet werden die [Typeid](../../cpp/typeid-operator.md) Operator, um einen verwalteten oder WinRT-Typ; verwenden Sie [Typeid](../../extensions/typeid-cpp-component-extensions.md) stattdessen.

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
