---
title: Compilerfehler C3354
ms.date: 11/04/2016
f1_keywords:
- C3354
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
ms.openlocfilehash: 1ff2967f602722c99b58b679324bd4f50575f109
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523158"
---
# <a name="compiler-error-c3354"></a>Compilerfehler C3354

"Funktion": Die zum Erstellen eines Delegaten verwendete Funktion kann nicht den Rückgabetyp "Typ" haben.

Die folgenden Typen sind keine gültigen Rückgabetypen für einen `delegate`:

- Zeiger auf Funktion

- Zeiger auf Member

- Zeiger auf Memberfunktion

- Verweis auf Funktion

- Verweis auf Memberfunktion

Im folgenden Beispiel wird C3354 generiert:

```
// C3354_2.cpp
// compile with: /clr /c
using namespace System;
typedef void ( *VoidPfn )();

delegate VoidPfn func(); // C3354
// try the following line instead
// delegate  void func();
```
