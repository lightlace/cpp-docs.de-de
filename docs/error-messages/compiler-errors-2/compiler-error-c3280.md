---
title: Compilerfehler C3280
ms.date: 11/04/2016
f1_keywords:
- C3280
helpviewer_keywords:
- C3280
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
ms.openlocfilehash: b43ea73a626ba35f58054a94046915d4eba97181
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382046"
---
# <a name="compiler-error-c3280"></a>Compilerfehler C3280

"Klasse": Eine Memberfunktion eines verwalteten Typs kann nicht als eine nicht verwaltete Funktion kompiliert werden

Es ist nicht möglich, Memberfunktionen mit verwalteten Klassen als nicht verwaltete Funktionen zu kompilieren.

Im folgenden Beispiel wird C3280 generiert:

```
// C3280_2.cpp
// compile with: /clr
ref struct A {
   void func();
};

#pragma managed(push,off)

void A::func()   // C3280
{
}

#pragma managed(pop)
```
