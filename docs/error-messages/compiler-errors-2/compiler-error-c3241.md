---
title: Compilerfehler C3241
ms.date: 11/04/2016
f1_keywords:
- C3241
helpviewer_keywords:
- C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
ms.openlocfilehash: 6eab22a8627b817b7a31e4bd34aad86d1f274615
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173500"
---
# <a name="compiler-error-c3241"></a>Compilerfehler C3241

'Methode': Diese Methode wurde nicht von 'Schnittstelle' eingeführt

Wenn Sie eine Funktion explizit überschreiben, muss die Funktionssignatur exakt die Deklaration für die Funktion, die Sie überschreiben.

Im folgende Beispiel wird die C3241 generiert:

```
// C3241.cpp
#pragma warning(disable:4199)

__interface IX12A {
   void mf();
};

__interface IX12B {
   void mf(int);
};

class CX12 : public IX12A, public IX12B { // C3241
   void IX12A::mf(int);
};
```