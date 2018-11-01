---
title: Compilerfehler C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: 63f9594eb9ee8a251faafe7323418b343c03063c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618025"
---
# <a name="compiler-error-c2507"></a>Compilerfehler C2507

'Bezeichner': zu viele virtuelle Modifizierer für Basisklasse

Eine Klasse oder Struktur wird als deklariert `virtual` mehr als einmal. Nur ein `virtual` Modifizierer kann für jede Klasse in einer Liste der Basisklassen verwendet werden.

Im folgende Beispiel wird die C2507 generiert:

```
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```