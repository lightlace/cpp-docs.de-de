---
title: Compilerfehler C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: 7bd87f0732e1a632b8c86cc57fab1a0f104b2c77
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755498"
---
# <a name="compiler-error-c2571"></a>Compilerfehler C2571

"Funktion": die virtuelle Funktion kann nicht in Union "Union" sein.

Eine Union wird mit einer virtuellen Funktion deklariert. Sie können eine virtuelle Funktion nur in einer Klasse oder Struktur deklarieren.  Mögliche Lösungen:

1. Ändern Sie die Union in eine Klasse oder Struktur.

1. Erstellen Sie die Funktion als nicht virtuell.

Im folgenden Beispiel wird C2571 generiert:

```cpp
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```
