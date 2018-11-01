---
title: Compilerwarnung (Stufe 4) C4263
ms.date: 11/04/2016
f1_keywords:
- C4263
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
ms.openlocfilehash: a035646aab2589523adb9eb0b201e2d4d781632c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555284"
---
# <a name="compiler-warning-level-4-c4263"></a>Compilerwarnung (Stufe 4) C4263

'Funktion': Memberfunktion überschreibt keine virtuelle Memberfunktion einer Basisklasse nicht

Definition einer Klasse hat den gleichen Namen wie eine virtuelle Funktion in eine Basisklasse, aber nicht die gleiche Anzahl oder Typ der Argumente. Dadurch wird effektiv die virtuelle Funktion in der Basisklasse ausgeblendet.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgende Beispiel wird die C4263 generiert:

```
// C4263.cpp
// compile with: /W4
#pragma warning(default:4263)
#pragma warning(default:4264)
class B {
public:
   virtual void func();
};

class D : public B {
   void func(int);   // C4263
};

int main() {
}
```