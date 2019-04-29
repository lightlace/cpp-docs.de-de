---
title: Compilerfehler C3364
ms.date: 11/04/2016
f1_keywords:
- C3364
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
ms.openlocfilehash: e99ab3919edcfb883701c08c52cd7aad60cd4591
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400356"
---
# <a name="compiler-error-c3364"></a>Compilerfehler C3364

'Delegat': Delegatkonstruktor: das Argument muss ein Zeiger auf Memberfunktion einer verwalteten Klasse oder einer globalen Funktion sein

Der zweite Parameter des Delegatkonstruktors verwendet entweder die Adresse einer Memberfunktion oder die Adresse einer statischen Memberfunktion einer Klasse. Beide werden als einfache Adressen behandelt.

Im folgende Beispiel wird die C3364 generiert:

```
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
