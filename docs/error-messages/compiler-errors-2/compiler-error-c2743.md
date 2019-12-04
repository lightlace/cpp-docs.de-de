---
title: Compilerfehler C2743
ms.date: 11/04/2016
f1_keywords:
- C2743
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
ms.openlocfilehash: d679ce0df0d43772a6c32aa8e00869ac1a4a082b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759645"
---
# <a name="compiler-error-c2743"></a>Compilerfehler C2743

"Typ": ein System eigener Typ kann nicht mit __clrcall Dekonstruktor oder Kopierkonstruktor abgefangen werden.

Ein Modul, das mit **/CLR** kompiliert wurde, hat versucht, eine Ausnahme vom systemeigenen Typ abzufangen, und der Dekonstruktor oder der Kopierkonstruktor des Typs verwendet `__clrcall` Aufruf Konvention.

Bei der Kompilierung mit **/CLR**erwartet die Ausnahmebehandlung, dass die Member-Funktionen in einem systemeigenen Typ [__cdecl](../../cpp/cdecl.md) und nicht [__clrcall](../../cpp/clrcall.md)werden. Systemeigene Typen mit Element Funktionen, die `__clrcall` Aufruf Konvention verwenden, können in einem mit **/CLR**kompilierten Modul nicht abgefangen werden.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2743 generiert.

```cpp
// C2743.cpp
// compile with: /clr
public struct S {
   __clrcall ~S() {}
};

public struct T {
   ~T() {}
};

int main() {
   try {}
   catch(S) {}   // C2743
   // try the following line instead
   // catch(T) {}

   try {}
   catch(S*) {}   // OK
}
```
