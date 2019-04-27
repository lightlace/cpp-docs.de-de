---
title: Compilerfehler C3244
ms.date: 11/04/2016
f1_keywords:
- C3244
helpviewer_keywords:
- C3244
ms.assetid: dae6c49b-5212-4206-8f61-d4010c0b9969
ms.openlocfilehash: fe17ac0f20c5644fd5bb81094242403b244bd1d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174925"
---
# <a name="compiler-error-c3244"></a>Compilerfehler C3244

'methode': Diese Methode wurde von 'schnittstelle' eingeführt, nicht von 'schnittstelle'

Versuch zum [expliziten Überschreiben](../../cpp/explicit-overrides-cpp.md) eines Members, der in der angegebenen Schnittstelle nicht vorhanden ist, wohl aber in einer anderen Basisklasse.

Im folgenden Beispiel wird C3244 generiert:

```
// C3244.cpp
#pragma warning(disable:4199)

__interface IX15A {
   void f();
};

__interface IX15B {
   void g();
};

class CX15 : public IX15A, public IX15B {
public:
   void IX15A::f();
   void IX15B::g();
};

void CX15::IX15A::g()   // C3244 occurs here
{
}
```