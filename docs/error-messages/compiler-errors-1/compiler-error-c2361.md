---
title: Compilerfehler C2361
ms.date: 11/04/2016
f1_keywords:
- C2361
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
ms.openlocfilehash: ca03a42cbf746a1ef32d9c79c23de637f05b56fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597105"
---
# <a name="compiler-error-c2361"></a>Compilerfehler C2361

Initialisierung von "Bezeichner" durch "Default"-Bezeichnung übersprungen

Die Initialisierung des `identifier` übersprungen werden kann, einem `switch` Anweisung. Sie können nicht hinter einer Deklaration mit einem Initialisierer springen, es sei denn, die Deklaration in einem Block eingeschlossen ist. (Es sei denn, sie innerhalb eines Blocks deklariert wird, wird die Variable Geltungsbereich bis zum Ende der `switch` Anweisung.)

Im folgende Beispiel wird die C2361 generiert:

```
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

```
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