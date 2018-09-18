---
title: Compilerfehler C2361 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2361
dev_langs:
- C++
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d91ee8b004e2f485326378eb2e1611f217f745c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029792"
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