---
title: Compilerfehler C3451 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3451
dev_langs:
- C++
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8685b75684827b4f202317e1df72a8248f1b41dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085198"
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