---
title: Compilerfehler C2555
ms.date: 11/04/2016
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: cc6c3a3a29665ccf65b77a3d9866986cb0a46b9e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353211"
---
# <a name="compiler-error-c2555"></a>Compilerfehler C2555

'Class1 ':: function1: überschreibende virtuelle Funktion unterscheidet sich und ist nicht von 'Class2 ':: function2 kovariant zurückgeben

Haben eine virtuelle Funktion und die abgeleiteten überschreibenden Funktion Parameterlisten identisch, jedoch unterschiedliche Rückgabetypen. Eine überschreibende-Funktion in einer abgeleiteten Klasse kann nicht von einer virtuellen Funktion in einer Basisklasse nur durch ihren Rückgabetyp unterscheiden.

Um diesen Fehler zu beheben, wandeln Sie den Rückgabewert, nachdem die virtuelle Funktion aufgerufen wurde.

Dieser Fehler kann auch angezeigt, wenn Sie mit "/ CLR" kompilieren.   Z. B. Visual C++ entspricht der folgenden C#-Deklaration:

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

echt

```
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

Im folgende Beispiel wird die C2555 generiert:

```cpp
// C2555.cpp
// compile with: /c
struct X {
   virtual void func();
};
struct Y : X {
   char func();  // C2555
   void func2();   // OK
};
```