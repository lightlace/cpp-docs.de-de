---
title: Compilerfehler C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: 226fcd8a27c9abdb789b8191a5cf4e59cc4a66cc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759905"
---
# <a name="compiler-error-c2360"></a>Compilerfehler C2360

die Initialisierung von "Identifier" wird von der Case-Bezeichnung übersprungen.

Die Initialisierung `identifier` kann in einer `switch` Anweisung übersprungen werden. Sie können nur dann eine Deklaration mit einem Initialisierer überspringen, wenn die Deklaration in einen-Block eingeschlossen ist. (Sofern Sie nicht in einem-Block deklariert wird, befindet sich die Variable bis zum Ende der `switch` Anweisung im Gültigkeitsbereich.)

Im folgenden Beispiel wird C2360 generiert:

```cpp
// C2360.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      int i = 1;
      { int j = 1; }
   case 1 :   // C2360
      int k = 1;
   }
}
```

Mögliche Lösung:

```cpp
// C2360b.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      { int j = 1; int i = 1;}
   case 1 :
      int k = 1;
   }
}
```
