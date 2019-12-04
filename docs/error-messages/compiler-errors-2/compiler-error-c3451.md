---
title: Compilerfehler C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: 2e0122dd53ba5318077dd33f22a07492c52db26b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756213"
---
# <a name="compiler-error-c3451"></a>Compilerfehler C3451

' Attribut ': das nicht verwaltete Attribut kann nicht auf ' type ' angewendet werden.

Ein C++ -Attribut kann nicht auf einen CLR-Typ angewendet werden. Weitere [ C++ ](../../windows/attributes/attributes-alphabetical-reference.md) Informationen finden Sie in der Referenz zu Attributen.

Weitere Informationen finden Sie unter [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md).

Dieser Fehler kann als Folge der für Visual Studio 2005 durchgeführten compilerübereinstimmungs-Arbeit generiert werden: das [UUID](../../windows/uuid-cpp-attributes.md) -Attribut ist für ein benutzerdefiniertes Attribut nicht mehr mithilfe der CLR-Programmierung zulässig. Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.GuidAttribute> .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3451 generiert.

```cpp
// C3451.cpp
// compile with: /clr /c
using namespace System;
[ attribute(AttributeTargets::All) ]
public ref struct MyAttr {};

[ MyAttr, helpstring("test") ]   // C3451
// try the following line instead
// [ MyAttr ]
public ref struct ABC {};
```
