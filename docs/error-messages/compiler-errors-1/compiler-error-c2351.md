---
title: Compilerfehler C2351
ms.date: 11/04/2016
f1_keywords:
- C2351
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
ms.openlocfilehash: 2d93902ee0008a54da1b2ecf165e0a829362511f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665490"
---
# <a name="compiler-error-c2351"></a>Compilerfehler C2351

Veraltete Syntax von C++-Konstruktor Initialisierung

In einer Initialisierungsliste neuer Formatvorlage für einen Konstruktor müssen Sie jeder direkte Basisklasse explizit benennen, auch wenn es sich um die einzige Basisklasse ist.

Im folgende Beispiel wird die C2351 generiert:

```
// C2351.cpp
// compile with: /c
class B {
public:
   B() : () {}   // C2351
   B() {}   // OK
};
```