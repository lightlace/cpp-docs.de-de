---
title: Compilerfehler C3364
ms.date: 11/04/2016
f1_keywords:
- C3364
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
ms.openlocfilehash: eae1e7ddbc34d36b55d7afa424c137db00ef047d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757344"
---
# <a name="compiler-error-c3364"></a>Compilerfehler C3364

"Delegat": Delegatkonstruktor: das Argument muss ein Zeiger auf eine Member-Funktion der verwalteten Klasse oder globalen Funktion sein.

Der zweite Parameter des Konstruktors des Delegaten übernimmt entweder die Adresse einer Member-Funktion oder die Adresse einer statischen Member-Funktion einer beliebigen Klasse. Beide werden als einfache Adressen behandelt.

Im folgenden Beispiel wird C3364 generiert:

```cpp
// C3364_2.cpp
// compile with: /clr

delegate int D( int, int );

ref class C {
public:
   int mf( int, int ) {
      return 1;
   }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC,pC->mf( 1, 2 ) ); // C3364

   // try the following line instead
   // System::Delegate^ pD = gcnew D(pC, &C::mf);
}
```
