---
title: Compilerfehler C2878
ms.date: 11/04/2016
f1_keywords:
- C2878
helpviewer_keywords:
- C2878
ms.assetid: 83ee3de1-f554-49e8-a840-1f550cee7f69
ms.openlocfilehash: f4570b7a2746386c66f8aa783f9270efb15d4765
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642778"
---
# <a name="compiler-error-c2878"></a>Compilerfehler C2878

"Name": Namespace oder Klasse dieses Namens ist nicht vorhanden.

Sie haben auf einen Namespace oder Klasse, die nicht definiert ist.

Im folgende Beispiel wird die C2878 generiert:

```
// C2878.cpp
// compile with: /c
namespace A {}
namespace B = C;   // C2878 namespace C doesn't exist
namespace B = A;
```