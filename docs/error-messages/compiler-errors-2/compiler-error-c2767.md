---
title: Compilerfehler C2767
ms.date: 11/04/2016
f1_keywords:
- C2767
helpviewer_keywords:
- C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
ms.openlocfilehash: 78b171b634aea66115c4029c696fec042593bb30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258096"
---
# <a name="compiler-error-c2767"></a>Compilerfehler C2767

verwaltet oder WinRTarray Dimensions-Konflikt: erwartet wurde(n) N Argument(e) - wurden M bereitgestellt

Die Deklaration eines verwalteten oder WinRT-Arrays wurde nicht ordnungsgemäß formatiert. Weitere Informationen finden Sie unter [Array](../../extensions/arrays-cpp-component-extensions.md).

Im folgenden Beispiel wird C2767 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2767.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>(2,3); // C2767
   array<int> ^p2 = new array<int>(2);   // OK
}
```