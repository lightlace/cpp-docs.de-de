---
title: Compilerfehler C3450
ms.date: 11/04/2016
f1_keywords:
- C3450
helpviewer_keywords:
- C3450
ms.assetid: 78892cf7-0b82-4589-90d0-e06666247003
ms.openlocfilehash: a5228e0396221c51f5fc7336255656416c1e553b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58780183"
---
# <a name="compiler-error-c3450"></a>Compilerfehler C3450

„Typ“: ist kein Attribut. [System::AttributeUsageAttribute] oder [Windows::Foundation::Metadata::AttributeUsageAttribute] darf nicht angegeben werden.

Ein benutzerdefiniertes verwaltetes Attribut muss von <xref:System.ComponentModel.AttributeCollection.%23ctor%2A> erben. Ein Windows-Runtime-Attribut muss im `Windows::Foundation::Metadata`-Namespace definiert sein.

Weitere Informationen finden Sie unter [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3450 generiert und gezeigt, wie Sie diesen Fehler beheben.

```
// C3450.cpp
// compile with: /clr
// C3450 expected
using namespace System;
using namespace System::Security;
using namespace System::Security::Permissions;

public ref class MyClass {};

class MyClass2 {};

[attribute(AttributeTargets::All)]
ref struct AtClass {
   AtClass(Type ^) {}
};

[attribute(AttributeTargets::All)]
ref struct AtClass2 {
   AtClass2() {}
};

// Apply the AtClass and AtClass2 attributes to class B
[AtClass(MyClass::typeid), AtClass2]
[AttributeUsage(AttributeTargets::All)]
// Delete the following line to resolve.
ref class B {};
// Uncomment the following line to resolve.
// ref class B : Attribute {};
```