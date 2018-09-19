---
title: Compilerfehler C3136 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 0439aa157a683065ccf7fff5b5f9d6d4d85e2f12
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054219"
---
# <a name="compiler-error-c3136"></a>Compilerfehler C3136

'Schnittstelle': eine COM-Schnittstelle kann nur von einem anderen COM-Schnittstelle erben, 'Schnittstelle' ist keine COM-Schnittstelle

Eine Schnittstelle, die auf die Sie angewendet ein [Interface-Attribut](../../windows/interface-attributes.md) erbt von einer Schnittstelle, die nicht auf eine COM-Schnittstelle ist. Eine COM-Schnittstelle erbt letztlich von `IUnknown`. Eine Schnittstelle, die vor dem Interface-Attribut ist eine COM-Schnittstelle.

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