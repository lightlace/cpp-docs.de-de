---
title: Compilerfehler C3136
ms.date: 10/03/2018
f1_keywords:
- C3136
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
ms.openlocfilehash: e32ffca067c3b25120301527e7a708d53001d541
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501089"
---
# <a name="compiler-error-c3136"></a>Compilerfehler C3136

'Schnittstelle': eine COM-Schnittstelle kann nur von einem anderen COM-Schnittstelle erben, 'Schnittstelle' ist keine COM-Schnittstelle

Eine Schnittstelle, die auf die Sie angewendet ein [Interface-Attribut](../../windows/attributes/interface-attributes.md) erbt von einer Schnittstelle, die nicht auf eine COM-Schnittstelle ist. Eine COM-Schnittstelle erbt letztlich von `IUnknown`. Eine Schnittstelle, die vor dem Interface-Attribut ist eine COM-Schnittstelle.

Im folgende Beispiel wird die C3136 generiert:

```
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