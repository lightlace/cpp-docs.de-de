---
title: Compilerfehler C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: f3e8f0ac260e49866d1c654f89d34bf57a8ffbc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463054"
---
# <a name="compiler-error-c2798"></a>Compilerfehler C2798

'super:: Member' ist mehrdeutig

Mehrere geerbte Strukturen enthalten den Member, die Sie verweist auf [super](../../cpp/super.md). Sie können den Fehler beheben, indem Sie entweder:

- Entfernen aus der Vererbungsliste von D. B1 oder B2

- Ändern den Namen des Datenelements in B1 oder B2.

Im folgende Beispiel wird die C2798 generiert:

```
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```