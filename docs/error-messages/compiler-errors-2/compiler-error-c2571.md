---
title: Compilerfehler C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: d7d4898e5f0b55c50a4c18cef053cc150394d7e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408576"
---
# <a name="compiler-error-c2571"></a>Compilerfehler C2571

"Function": virtuelle Funktion darf sich nicht in Union "Union"

Eine Union ist mit einer virtuellen Funktion deklariert. Sie können eine virtuelle Funktion nur in einer Klasse oder Struktur deklarieren.  Mögliche Lösungen:

1. Ändern Sie die Union in einer Klasse oder Struktur an.

1. Stellen Sie die Funktion nicht virtuell.

Im folgende Beispiel wird die C2571 generiert:

```
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```