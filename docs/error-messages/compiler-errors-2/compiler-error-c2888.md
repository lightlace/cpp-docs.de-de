---
title: Compilerfehler C2888
ms.date: 11/04/2016
f1_keywords:
- C2888
helpviewer_keywords:
- C2888
ms.assetid: 244f593e-ff25-4dad-b31f-84dafa3bc84a
ms.openlocfilehash: c5b547f1c4d62a6f48b6c5f8f901be309e81a67c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311904"
---
# <a name="compiler-error-c2888"></a>Compilerfehler C2888

'Bezeichner': Symbol kann nicht im Namespace 'Namespace' definiert werden

Ein Symbol, die auf ein-Namespace gehören muss in einem Namespace definiert werden, die a umschließt.

Im folgende Beispiel wird die C2888 generiert:

```
// C2888.cpp
// compile with: /c
namespace M {
   namespace N {
      void f1();
      void f2();
   }

   void N::f1() {}   // OK: namspace M encloses N
}

namespace O {
   void M::N::f2() {}   // C2888 namespace O does not enclose M
}
```