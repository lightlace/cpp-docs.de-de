---
title: Compilerwarnung (Stufe 4) C4242
ms.date: 11/04/2016
f1_keywords:
- C4242
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
ms.openlocfilehash: 3123a414dc7a169d2a472dad96d659a9e56c9020
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541750"
---
# <a name="compiler-warning-level-4-c4242"></a>Compilerwarnung (Stufe 4) C4242

' Identifier ': Konvertierung von ' Typ1 ' in ' Typ2 ', möglicher Datenverlust

Die Typen unterscheiden sich. Die Typkonvertierung kann zu Datenverlusten führen. Der Compiler führt die Typkonvertierung durch.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Weitere Informationen zu C4242 finden Sie unter [Häufige Compilerfehler](/windows/win32/WinProg64/common-compiler-errors).

Im folgenden Beispiel wird C4242 generiert:

```cpp
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