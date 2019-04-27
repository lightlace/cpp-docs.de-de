---
title: Compilerfehler C3095
ms.date: 11/04/2016
f1_keywords:
- C3095
helpviewer_keywords:
- C3095
ms.assetid: cde725be-0936-40f6-9e57-e1d7d0710f83
ms.openlocfilehash: d0cf35e7964925623be39c0177d77fc5a6231ad2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152487"
---
# <a name="compiler-error-c3095"></a>Compilerfehler C3095

"Attribut": Das Attribut kann nicht wiederholt werden.

Einige Attribute werden so deklariert, dass mehrere Vorkommen des Attributs auf ein Ziel angewendet werden können.

Weitere Informationen finden Sie unter [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3095 generiert.

```
// C3095.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All, AllowMultiple=false)]
public ref class Attr : public Attribute {
public:
   Attr(int t) : m_t(t) {}
   const int m_t;
};

[AttributeUsage(AttributeTargets::All, AllowMultiple=true)]
public ref class Attr2 : public Attribute {
public:
   Attr2(int t) : m_t(t) {}
   const int m_t;
};

[Attr(10)]   // C3095
[Attr(11)]
ref class A {};

[Attr2(10)]   // OK
[Attr2(11)]
ref class B {};
```