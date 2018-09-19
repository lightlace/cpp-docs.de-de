---
title: Compilerfehler C3707 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3707
dev_langs:
- C++
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d18d4a82d06018cdba6147ba6756b1718648847a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052782"
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