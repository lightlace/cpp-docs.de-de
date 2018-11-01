---
title: Compilerfehler C3763
ms.date: 11/04/2016
f1_keywords:
- C3763
helpviewer_keywords:
- C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
ms.openlocfilehash: e7dc73334cedda27b82f79b1d2b7a8fc38a8098d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581310"
---
# <a name="compiler-error-c3763"></a>Compilerfehler C3763

"Type": "Retval" und "Out" kann nur in einem Datenzeigertyp angezeigt werden.

Die [out](../../windows/out-cpp.md) oder [Retval](../../windows/retval.md) Attribute können nur auf Parameter des Typs Zeiger angezeigt werden. Entfernen Sie das Attribut oder stellen Sie den Parameter des Typs Zeiger.

Im folgende Beispiel wird die C3763 generiert:

```
// C3763.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlplus.h>
#include <atlcom.h>

[ module(name=test) ];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IF84 : IDispatch
{
   [id(0x00000002)]HRESULT m2([out]unsigned char);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]
class CF84 : public IF84
{   // C3763
public:
   HRESULT __stdcall m2(unsigned char i)
   {
      return S_OK;
   }
};

int main()
{
}
```