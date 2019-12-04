---
title: Compilerfehler C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: aa3e97d576e994878ab5b080363c4c09b79f42ed
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756785"
---
# <a name="compiler-error-c2553"></a>Compilerfehler C2553

"Base_function": der Rückgabetyp der virtuellen Funktion unterscheidet sich von "override_function".

Eine Funktion in einer abgeleiteten Klasse hat versucht, eine virtuelle Funktion in einer Basisklasse zu überschreiben, aber die abgeleitete Klassen Funktion hat nicht denselben Rückgabetyp wie die Basisklassen Funktion.  Eine Überschreibungs Funktions Signatur muss mit der Signatur der Funktion identisch sein, die überschrieben wird.

Im folgenden Beispiel wird C2553 generiert:

```cpp
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
