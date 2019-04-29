---
title: Compilerfehler C3265
ms.date: 11/04/2016
f1_keywords:
- C3265
helpviewer_keywords:
- C3265
ms.assetid: 10ab3e17-4a9f-4120-bab5-21473869b70f
ms.openlocfilehash: a675567e23764a0b361cab4bef4bc75019de3756
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365844"
---
# <a name="compiler-error-c3265"></a>Compilerfehler C3265

ein verwaltete 'verwaltetes Konstrukt' aus, in eine nicht verwaltete 'nicht verwalteten Konstrukt' kann nicht deklariert werden.

Sie können kein verwaltetes Objekt in einem nicht verwalteten Kontext einschließen.

Im folgende Beispiel wird die C3265 reproduziert:

```
// C3265_2.cpp
// compile with: /clr /LD
#include <vcclr.h>

ref class A { };

class B
// try the following line instead
// ref class B
{
   A ^a;   // C3265
   // or embed the managed handle using gcroot
   // try the following line instead
   // gcroot<A^> a;
};
```
