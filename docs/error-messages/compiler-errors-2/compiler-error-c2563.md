---
title: Compilerfehler C2563
ms.date: 11/04/2016
f1_keywords:
- C2563
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
ms.openlocfilehash: 983788f041651fcd313c0707a4a7c64cc6e33c5a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755537"
---
# <a name="compiler-error-c2563"></a>Compilerfehler C2563

nicht übereinstimmende Liste der formalen Parameter.

Die Liste der formalen Parameter einer Funktion (oder eines Zeigers auf eine Funktion) stimmt nicht mit denen einer anderen Funktion (oder einem Zeiger auf eine Member-Funktion) identisch. Daher kann die Zuweisung von Funktionen oder Zeigern nicht durchgeführt werden.

Im folgenden Beispiel wird C2563 generiert:

```cpp
// C2563.cpp
void func( int );
void func( int, int );
int main() {
   void *fp();
   fp = func;   // C2563
}
```
