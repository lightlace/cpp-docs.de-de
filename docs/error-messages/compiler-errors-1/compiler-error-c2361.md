---
title: Compilerfehler C2361
ms.date: 11/04/2016
f1_keywords:
- C2361
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
ms.openlocfilehash: 747b85b57bee9e53f13a978254798a1dc268ef85
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759892"
---
# <a name="compiler-error-c2361"></a>Compilerfehler C2361

die Initialisierung von "Identifier" wird von der Bezeichnung "Default" übersprungen.

Die Initialisierung `identifier` kann in einer `switch` Anweisung übersprungen werden. Sie können nur dann eine Deklaration mit einem Initialisierer überspringen, wenn die Deklaration in einen-Block eingeschlossen ist. (Sofern Sie nicht in einem-Block deklariert wird, befindet sich die Variable bis zum Ende der `switch` Anweisung im Gültigkeitsbereich.)

Im folgenden Beispiel wird C2361 generiert:

```cpp
// C2361.cpp
void func( void ) {
   int x;
   switch (x) {
   case 0 :
      int i = 1;
      { int j = 1; }
   default :   // C2361 error
      int k = 1;
   }
}
```

Mögliche Lösung:

```cpp
// C2361b.cpp
// compile with: /c
void func( void ) {
   int x = 0;
   switch (x) {
   case 0 :
      { int j = 1; int i = 1;}
   default :
      int k = 1;
   }
}
```
