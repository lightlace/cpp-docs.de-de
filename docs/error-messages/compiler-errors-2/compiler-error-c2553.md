---
title: Compilerfehler C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: 11cb2b83d958f0c59d05034a716a022f00b326ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658678"
---
# <a name="compiler-error-c2553"></a>Compilerfehler C2553

'Basisfunktion': Typ unterscheidet sich von 'Überschreibungsfunktion' überschreibende virtuelle Funktion zurückgegeben werden

Eine Funktion in einer abgeleiteten Klasse hat versucht, eine virtuelle Funktion in einer Basisklasse überschreiben, aber die abgeleitete Klassenfunktion haben nicht den gleichen Rückgabetyp als Funktion der Basisklasse.  Eine außer Kraft setzen-Funktion-Signatur muss es sich um die Signatur der Funktion überschrieben werden übereinstimmen.

Im folgende Beispiel wird die C2553 generiert:

```
// C2553.cpp
// compile with: /clr /c
ref struct C {
   virtual void f();
};

ref struct D : C {
   virtual int f() override ;   // C2553

   // try the following line instead
   // virtual void f() override;
};
```