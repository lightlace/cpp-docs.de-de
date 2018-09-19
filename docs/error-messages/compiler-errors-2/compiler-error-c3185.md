---
title: Compilerfehler C3185 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3185
dev_langs:
- C++
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd7f94f86165fdfd25bb5a901cdb4349a0e48494
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044521"
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
