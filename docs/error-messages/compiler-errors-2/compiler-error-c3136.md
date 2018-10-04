---
title: Compilerfehler C3136 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3136
dev_langs:
- C++
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 082a89b69092a8320f6bb4b930d01a7fd2de10c8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788382"
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