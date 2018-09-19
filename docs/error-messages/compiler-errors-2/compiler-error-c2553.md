---
title: Compilerfehler C2553 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2553
dev_langs:
- C++
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38fb61b7281dd0371c546fd7b7bc960232cf2e00
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043988"
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