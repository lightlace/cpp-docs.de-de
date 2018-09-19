---
title: Compilerwarnung (Stufe 1) C4683 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a157d3beb7c2efa7f1144a961973652e2ce384f7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194196"
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