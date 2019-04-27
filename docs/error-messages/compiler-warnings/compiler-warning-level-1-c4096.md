---
title: Compilerwarnung (Stufe 1) C4096
ms.date: 11/04/2016
f1_keywords:
- C4096
helpviewer_keywords:
- C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
ms.openlocfilehash: 287465e9a3f5681f459f0823a4409b0906309a55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280456"
---
# <a name="compiler-warning-level-1-c4096"></a>Compilerwarnung (Stufe 1) C4096

"a": Schnittstelle ist nicht mit einem COM-Schnittstelle wird nicht nach IDL emittiert

Eine Schnittstellendefinition, die Sie als COM-Schnittstelle für verfügen möglicherweise nicht als COM-Schnittstelle definiert wurde und daher nicht ausgegeben, um die IDL-Datei.

Finden Sie unter [Schnittstellenattribute](../../windows/attributes/interface-attributes.md) für eine Liste der Attribute, die angeben, eine Schnittstelle ist eine COM-Schnittstelle.

Im folgende Beispiel wird die C4096 generiert:

```
// C4096.cpp
// compile with: /W1 /LD
#include "windows.h"
[module(name="xx")];

// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct b : a
{
};   // C4096, remove coclass or uncomment object
```