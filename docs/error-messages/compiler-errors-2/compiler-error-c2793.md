---
title: Compilerfehler C2793
ms.date: 11/04/2016
f1_keywords:
- C2793
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
ms.openlocfilehash: 5533a0e8f75a1a513fbabe451fb41629a4595382
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360150"
---
# <a name="compiler-error-c2793"></a>Compilerfehler C2793

'token': folgen unerwartete token "::", Bezeichner oder Schlüsselwort "Operator" erwartet

Die einzigen Token, die folgen können `__super::` sind ein Bezeichner oder das Schlüsselwort `operator`.

Im folgende Beispiel wird C2793 generiert:

```
// C2793.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::(); // C2793
   }
};
```