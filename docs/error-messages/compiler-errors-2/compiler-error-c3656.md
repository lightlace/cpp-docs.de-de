---
title: Compilerfehler C3656
ms.date: 11/04/2016
f1_keywords:
- C3656
helpviewer_keywords:
- C3656
ms.assetid: 88965d85-73b0-4b35-8020-0650c9c94cd8
ms.openlocfilehash: 9709f3105e957012c05111ea818890b6d1df8259
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227056"
---
# <a name="compiler-error-c3656"></a>Compilerfehler C3656

"override": Überschreiben der Bezeichner kann nicht wiederholt werden

Eine explizite Überschreibung-Schlüsselwort kann nur einmal angegeben werden. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../extensions/explicit-overrides-cpp-component-extensions.md).

Im folgende Beispiel wird die C3656 generiert:

```
// C3656.cpp
// compile with: /clr /c
public interface struct O {
   int f();
};

public ref struct V : O {
   int f() override override { return 0; }   // C3656
   // try the following line instead
   // int f() override { return 0; }
};
```