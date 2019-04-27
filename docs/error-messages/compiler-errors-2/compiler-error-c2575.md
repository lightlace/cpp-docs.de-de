---
title: Compilerfehler C2575
ms.date: 11/04/2016
f1_keywords:
- C2575
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
ms.openlocfilehash: 2737f9078e1c17358e3c975a5c3f8b6d211fd308
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165774"
---
# <a name="compiler-error-c2575"></a>Compilerfehler C2575

'Bezeichner': nur Memberfunktionen und Basisklasse können virtuell sein

Eine globale Funktion oder Klasse deklariert wird `virtual`. Dies ist nicht zulässig.

Im folgende Beispiel wird die C2575 generiert:

```
// C2575.cpp
// compile with: /c
virtual void func() {}   // C2575

void func2() {}
struct A {
   virtual void func2(){}
};
```