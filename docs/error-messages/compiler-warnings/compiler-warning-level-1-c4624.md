---
title: Compilerwarnung (Stufe 1) C4624
ms.date: 11/04/2016
f1_keywords:
- C4624
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
ms.openlocfilehash: b1a7d715057f4c6d8ada104ad07f6ad0b9c52fb2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221390"
---
# <a name="compiler-warning-level-1-c4624"></a>Compilerwarnung (Stufe 1) C4624

'derived class': Der Destruktor wurde impliziert als gelöscht definiert, da ein Basisklassen-Destruktor nicht zugreifbar ist oder gelöscht wurde.

Ein Destruktor stand nicht für den Zugriff zur Verfügung oder wurde in einer Basisklasse gelöscht. Daher wurde er nicht für eine abgeleitete Klasse generiert. Jeder Versuch, ein Objekt dieses Typs auf dem Stapel zu erstellen, verursacht einen Compilerfehler.

Im folgenden Beispiel wird C4624 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C4624.cpp
// compile with: /W1 /c
class B {
// Uncomment the following line to fix.
// public:
   ~B();
};

class D : public B {};   // C4624 B's destructor not public
```