---
title: Compilerwarnung (Stufe 1) C4683
ms.date: 08/27/2018
f1_keywords:
- C4683
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
ms.openlocfilehash: 264753ece6cbabded21df8e6b9dbb463f811e8a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375157"
---
# <a name="compiler-warning-level-1-c4683"></a>Compilerwarnung (Stufe 1) C4683

> "*Funktion*': Ereignisquelle hat einen"Out"-Parameter. Seien Sie vorsichtig, wenn mehrere Ereignishandler eine Hookfunktion erstellen

## <a name="remarks"></a>Hinweise

Wenn mehr als eine Ereignissenke, eine COM-Ereignisquelle abhört, kann der Wert eines Ausgabeparameters ignoriert.

Achten Sie darauf, dass ein Speicherverlust in den folgenden Situationen auftritt, sind:

1. Wenn eine Methode einen Out-Parameter, der intern zugeordnet ist hat, z. B. einen BSTR *.

2. Wenn das Ereignis mit mehr als einen Handler verfügt (ein multicast-Ereignis ist).

Der Grund für den Verlusten ist, dass der Out-Parameter wird von mehr als einen Handler festgelegt, aber nur von der letzte Handler an der Aufrufsite zurückgegeben.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4683 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C4683.cpp
// compile with: /W1 /LD
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="xx") ];

[ object ]
__interface I {
   HRESULT f([out] int* pi);
   // try the following line instead
   // HRESULT f(int* pi);
};

[ coclass, event_source(com) ]
struct E {
   __event __interface I;   // C4683
};
```