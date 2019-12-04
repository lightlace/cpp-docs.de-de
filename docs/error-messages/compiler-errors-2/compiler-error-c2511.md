---
title: Compilerfehler C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: ff78cb50b274fe40d513739264bd7e9894bbed9d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746564"
---
# <a name="compiler-error-c2511"></a>Compilerfehler C2511

"Bezeichner": überladene Member-Funktion wurde in "Class" nicht gefunden.

Es wurde keine Version der Funktion mit den angegebenen Parametern deklariert.  Mögliche Ursachen:

1. An die Funktion wurden falsche Parameter übermittelt.

1. Parameter wurden in falscher Reihenfolge übermittelt.

1. Falsche Schreibweise von Parameternamen.

Im folgenden Beispiel wird C2511 generiert:

```cpp
// C2511.cpp
// compile with: /c
class C {
   int c_2;
   int Func(char *, char *);
};

int C::Func(char *, char *, int i) {   // C2511
// try the following line instead
// int C::Func(char *, char *) {
   return 0;
}
```
