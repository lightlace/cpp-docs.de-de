---
title: Compilerwarnung (Stufe 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: 05984594a57878aad8037861a15ac9284ff65192
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521228"
---
# <a name="compiler-warning-level-1-c4190"></a>Compilerwarnung (Stufe 1) C4190

'Bezeichner1' C-Bindung angegeben wurde, aber gibt UDT "Bezeichner2" ist nicht mit C

Eine Funktion oder ein Zeiger auf Funktion verfügt über ein UDT (benutzerdefinierte Typ, die eine Klasse, Struktur, Enumeration oder Union ist) als Rückgabetyp und `extern` "C"-Verknüpfung. Dies ist zulässig wenn:

- Alle Aufrufe dieser Funktion auftreten von C++.

- Die Definition der Funktion ist in C++.

## <a name="example"></a>Beispiel

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```