---
title: Compilerfehler C2689
ms.date: 11/04/2016
f1_keywords:
- C2689
helpviewer_keywords:
- C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
ms.openlocfilehash: fb9a45f775da582daa0fbe421f29b6e469a91197
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484551"
---
# <a name="compiler-error-c2689"></a>Compilerfehler C2689

'Funktion': eine Friend-Funktion kann nicht innerhalb einer lokalen Klasse definiert werden

Sie können deklarieren, aber keine Friend-Funktion in einer lokalen Klasse definiert.

Im folgende Beispiel wird die C2689 generiert:

```
// C2689.cpp
// compile with: /c
void g() {
   void f2();
   class X {
      friend void f2(){}   // C2689
      friend void f2();   // OK
   };
}
```