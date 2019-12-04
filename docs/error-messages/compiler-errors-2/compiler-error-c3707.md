---
title: Compilerfehler C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: 6faf035c0f4f68b10b187c56bea4cafc776998cf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757955"
---
# <a name="compiler-error-c3707"></a>Compilerfehler C3707

"Function": die dispinterface-Methode muss eine "DISPID" aufweisen.

Wenn Sie eine `dispinterface` Methode verwenden, müssen Sie Ihr eine `dispid`zuweisen. Um diesen Fehler zu beheben, weisen Sie der `dispinterface`-Methode einen `dispid` zu, indem Sie beispielsweise das `id`-Attribut für die-Methode im folgenden Beispiel auskommentieren. Weitere Informationen finden Sie in den Attributen " [dispinterface](../../windows/dispinterface.md) " und " [ID](../../windows/id.md)".

Im folgenden Beispiel wird C3707 generiert:

```cpp
// C3707.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(name="xx")];
[dispinterface]
__interface IEvents : IDispatch
{
   HRESULT event1([in] int i);   // C3707
   // try the following line instead
   // [id(1)] HRESULT event1([in] int i);
};

int main() {
}
```
