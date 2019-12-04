---
title: Compilerfehler C3340
ms.date: 11/04/2016
f1_keywords:
- C3340
helpviewer_keywords:
- C3340
ms.assetid: 23b12298-b92a-4717-8380-f165c998cb8a
ms.openlocfilehash: f4010870b84cbe2b8004eea24ab7735839b8c82b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753587"
---
# <a name="compiler-error-c3340"></a>Compilerfehler C3340

'Schnittstelle': Die Schnittstelle kann in der Co-Klasse 'Klasse' nicht zugleich 'restricted' und 'default' sein.

Das [restricted](../../windows/restricted.md) -Attribut und das [default](../../windows/default-cpp.md) -Attribut schließen sich gegenseitig aus.

Im folgenden Beispiel wird C3340 generiert:

```cpp
// C3340.cpp
#include <windows.h>
[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface
{
   HRESULT f1();
};

[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f),
default(IMyIface),
source(IMyIface),restricted(IMyIface) ]
class CmyClass // C3340
{
};

int main()
{
}
```
