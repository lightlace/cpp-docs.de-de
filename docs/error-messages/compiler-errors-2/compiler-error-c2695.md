---
title: Compilerfehler C2695
ms.date: 11/04/2016
f1_keywords:
- C2695
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
ms.openlocfilehash: 6d46699a2036c4f45daf3c34802ddb6b44e554ff
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755212"
---
# <a name="compiler-error-c2695"></a>Compilerfehler C2695

"Funktion1": die über schreibende virtuelle Funktion unterscheidet sich von "Funktion2" nur durch die Aufruf Konvention.

Die Signatur einer Funktion in einer abgeleiteten Klasse kann eine Funktion in einer Basisklasse nicht überschreiben und die Aufruf Konvention ändern.

Im folgenden Beispiel wird C2695 generiert:

```cpp
// C2695.cpp
class C {
   virtual void __fastcall func();
};

class D : public C {
   virtual void __clrcall func();   // C2695
};
```
