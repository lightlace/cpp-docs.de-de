---
title: Compilerwarnung (Stufe 4) C4263
ms.date: 11/04/2016
f1_keywords:
- C4263
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
ms.openlocfilehash: ed4b8561975f3d808781551e0d5f363d0d0088b8
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991442"
---
# <a name="compiler-warning-level-4-c4263"></a>Compilerwarnung (Stufe 4) C4263

"Function": die Member-Funktion überschreibt keine virtuelle Member-Funktion der Basisklasse.

Eine Klassen Funktionsdefinition hat denselben Namen wie eine virtuelle Funktion in einer Basisklasse, aber nicht die gleiche Anzahl oder Art von Argumenten. Dadurch wird die virtuelle Funktion in der Basisklasse ausgeblendet.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4263 generiert:

```cpp
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
