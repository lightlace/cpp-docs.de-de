---
title: Compilerfehler C2761
ms.date: 11/04/2016
f1_keywords:
- C2761
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
ms.openlocfilehash: 1236cfaf70781b6ca80db1a317a0c1b01b0f2740
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228231"
---
# <a name="compiler-error-c2761"></a>Compilerfehler C2761

'Funktion': die erneute Deklaration der Funktion nicht zulässig

Eine Memberfunktion kann nicht erneut deklariert werden. Sie können definieren, jedoch nicht neu deklariert werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2761 generiert.

```
// C2761.cpp
class a {
   int t;
   void test();
};

void a::a;     // C2761
void a::test;  // C2761
```

## <a name="example"></a>Beispiel

Nicht statische Member einer Klasse oder Struktur können nicht definiert werden.  Im folgende Beispiel wird die C2761 generiert.

```
// C2761_b.cpp
// compile with: /c
struct C {
   int s;
   static int t;
};

int C::s;   // C2761
int C::t;   // OK
```