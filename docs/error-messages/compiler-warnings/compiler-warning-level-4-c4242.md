---
title: Compilerwarnung (Stufe 4) C4242
ms.date: 11/04/2016
f1_keywords:
- C4242
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
ms.openlocfilehash: e0582f3dfdd223b4571e361dc69fae1990aeea1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498214"
---
# <a name="compiler-warning-level-4-c4242"></a>Compilerwarnung (Stufe 4) C4242

'Bezeichner': Konvertierung von 'type1' in 'type2', möglicher Datenverlust

Die Typen unterscheiden. Typkonvertierung kann zu Datenverlust führen. Der Compiler stellt die typkonvertierung.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Weitere Informationen über C4242, finden Sie unter [Häufige Compilerfehler](/windows/desktop/WinProg64/common-compiler-errors).

Im folgende Beispiel wird die C4242 generiert:

```
// C4242.cpp
// compile with: /W4
#pragma warning(4:4242)
int func() {
   return 0;
}

int main() {
   char a;
   a = func();   // C4242, return type and variable type do not match
}
```