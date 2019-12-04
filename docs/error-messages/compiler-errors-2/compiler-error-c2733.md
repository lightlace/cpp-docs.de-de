---
title: Compilerfehler C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: 3ef669a49f4a3ec5a1af1a15a79f2511fa2699dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755784"
---
# <a name="compiler-error-c2733"></a>Compilerfehler C2733

zweite C-Verknüpfung der überladenen Funktion "Funktion" nicht zulässig

Mehr als eine überladene Funktion wird mit C-Verknüpfung deklariert. Bei Verwendung der C-Verknüpfung kann nur eine Form einer angegebenen Funktion extern sein. Da überladene Funktionen denselben nicht ergänzten Namen aufweisen, können Sie nicht mit C-Programmen verwendet werden.

Im folgenden Beispiel wird C2733 generiert:

```cpp
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
