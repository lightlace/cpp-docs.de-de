---
title: Compilerfehler C2724
ms.date: 11/04/2016
f1_keywords:
- C2724
helpviewer_keywords:
- C2724
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
ms.openlocfilehash: 3014a12767cb9a73dc65852c544b7ac9574b9a52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585249"
---
# <a name="compiler-error-c2724"></a>Compilerfehler C2724

'Bezeichner':'static' sollte nicht für Memberfunktionen, die im Dateibereich definiert verwendet werden

Statische Memberfunktionen sollen mit externer Verknüpfung deklariert werden.

Im folgende Beispiel wird die C2724 generiert:

```
// C2724.cpp
class C {
   static void func();
};

static void C::func(){};   // C2724
// try the following line instead
// void C::func(){};
```