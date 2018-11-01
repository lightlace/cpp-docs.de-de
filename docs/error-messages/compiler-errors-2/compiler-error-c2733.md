---
title: Compilerfehler C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: 26819f1928223b5fa96d275290105f32787057f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518845"
---
# <a name="compiler-error-c2733"></a>Compilerfehler C2733

zweite C-Bindung für überladene Funktion 'Funktion' nicht zulässig

Mehr als einer überladenen Funktion mit C-Verknüpfung deklariert wird. Wenn Sie C-Bindung verwenden, kann nur eine Form von einer angegebenen Funktion externe sein. Da überladene Funktionen über den gleichen nicht ergänzten Namen verfügen, können sie mit der C-Programmen verwendet werden.

Im folgende Beispiel wird die C2733 generiert:

```
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```