---
title: Compilerwarnung (Stufe 4) C4242
ms.date: 11/04/2016
f1_keywords:
- C4242
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
ms.openlocfilehash: 2f457b5424cbca071e047f4375aaa85962e52210
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991484"
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
