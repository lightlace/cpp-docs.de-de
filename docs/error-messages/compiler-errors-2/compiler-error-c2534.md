---
title: Compilerfehler C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: e684804ea31b16f31c82e244cb4f9a6aaf2d08c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386966"
---
# <a name="compiler-error-c2534"></a>Compilerfehler C2534

"Bezeichner": Konstruktor kann keinen Wert zurückgeben

Ein Konstruktor kann keinen Wert zurückgeben oder keinen Rückgabetyp haben (nicht einmal eine `void` Rückgabetyp).

Dieser Fehler möglicherweise behoben werden, durch das Entfernen der `return` Anweisung aus der Konstruktordefinition.

Im folgende Beispiel wird die C2534 generiert:

```
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```