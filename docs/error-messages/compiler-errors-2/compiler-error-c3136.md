---
title: Compilerfehler C3136
ms.date: 10/03/2018
f1_keywords:
- C3136
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
ms.openlocfilehash: 75862f3b80d617b607a7b3e735cb3e16e9a40bb7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757383"
---
# <a name="compiler-error-c3136"></a>Compilerfehler C3136

"Interface": eine COM-Schnittstelle kann nur von einer anderen COM-Schnittstelle erben, "Interface" ist keine COM-Schnittstelle.

Eine Schnittstelle, auf die Sie ein [Schnittstellen Attribut](../../windows/attributes/interface-attributes.md) angewendet haben, erbt von einer Schnittstelle, die keine COM-Schnittstelle ist. Eine COM-Schnittstelle erbt letztendlich von `IUnknown`. Jede Schnittstelle, der ein Schnittstellen Attribut voransteht, ist eine COM-Schnittstelle.

Im folgenden Beispiel wird C3136 generiert:

```cpp
// C3136.cpp
#include "unknwn.h"

__interface A   // C3136
// try the following line instead
// _interface A : IUnknown
{
   int a();
};

[object]
__interface B : A
{
   int aa();
};
```
