---
title: Compilerfehler C3761
ms.date: 11/04/2016
f1_keywords:
- C3761
helpviewer_keywords:
- C3761
ms.assetid: 0c16f093-7a78-4838-b90b-0c67ef6e9270
ms.openlocfilehash: f3ac54b7f72cbcc8107aeaebaac4b8e824d3c315
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757266"
---
# <a name="compiler-error-c3761"></a>Compilerfehler C3761

"Function": "retval" kann nur im letzten Argument einer Funktion angezeigt werden.

Das [retval](../../windows/retval.md) -Attribut wurde für ein Funktions Argument verwendet, das nicht das letzte Argument in der Liste war.

Im folgenden Beispiel wird C3761 generiert:

```cpp
// C3761.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(name=test) ];

[dispinterface]
__interface I
{
   [id(1)] HRESULT func([out, retval] int* i, [in] int j);
   // try the following line instead
   // [id(1)] HRESULT func([in] int i, [out, retval] int* j);
};

[coclass]
struct C : I {   // C3761
   HRESULT func(int* i, int j)
   // try the following line instead
   // HRESULT func(int j, int* i)
   {
      return S_OK;
   }
};

int main()
{
}
```
