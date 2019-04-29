---
title: Compilerfehler C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: 8a1525539c84ea427815a03057bb6d2f9213fec7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328522"
---
# <a name="compiler-error-c3707"></a>Compilerfehler C3707

"Function": Dispinterface-Methode müssen eine Dispid

Bei Verwendung einer `dispinterface` -Methode müssen Sie sie Zuweisen einer `dispid`. Um diesen Fehler zu beheben, weisen eine `dispid` auf die `dispinterface` Methode, z. B. indem Sie die Kommentierung der `id` Attribut in der Methode im folgenden Beispiel. Weitere Informationen finden Sie auf die Attribute [Dispinterface](../../windows/dispinterface.md) und [Id](../../windows/id.md).

Im folgende Beispiel wird die C3707 generiert:

```
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