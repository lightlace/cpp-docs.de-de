---
title: Compilerfehler C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: 041c0c22b7ae842073bfd6656d9cbb3b2a20af9c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430055"
---
# <a name="compiler-error-c3451"></a>Compilerfehler C3451

'Attribut': nicht verwaltetes Attribut nach 'type' kann nicht angewendet

Ein C++-Attribut kann nicht in einen CLR-Typ angewendet werden. Finden Sie unter [C++-Attributreferenz](../../windows/cpp-attributes-reference.md) für Weitere Informationen.

Weitere Informationen finden Sie unter [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).

Dieser Fehler kann infolge einer konformitätsverbesserung für Compiler, die für Visual C++ 2005 durchgeführt wurde generiert werden: die [Uuid](../../windows/uuid-cpp-attributes.md) Attribut ist für ein benutzerdefiniertes Attribut mit der Programmierung der CLR nicht mehr zulässig. Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.GuidAttribute>.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3451 generiert.

```
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