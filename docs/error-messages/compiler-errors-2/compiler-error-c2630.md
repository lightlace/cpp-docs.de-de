---
title: Compilerfehler C2630 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2630
dev_langs:
- C++
helpviewer_keywords:
- C2630
ms.assetid: 7a655a9c-bab4-495b-97a3-a3f34cf5369a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2bcde84e241590b67e3877e3ce415f4cc00e757a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085939"
---
# <a name="compiler-error-c2630"></a>Compilerfehler C2630

'Symbol' finden Sie in Was sollte eine durch Trennzeichen getrennte Liste sein.

Das Symbol wird angezeigt, in einem Kontext, der ein Komma ist erforderlich.

Im folgende Beispiel wird die C2630 generiert:

```
// C2630.cpp
// compile with: /c
struct D {
   D(int);
};

struct E {
   E(int);
};

class C : public D, public E {
   C();
};

C::C() : D(0) ; E(0) { }   // C2630
C::C() : D(0), E(0) {}   // OK
```