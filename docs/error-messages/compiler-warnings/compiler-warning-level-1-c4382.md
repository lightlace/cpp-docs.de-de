---
title: Compilerwarnung (Stufe 1) C4382
ms.date: 11/04/2016
f1_keywords:
- C4382
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
ms.openlocfilehash: cca2f8cc13cc8317bac3736e142ef58e126ed994
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629215"
---
# <a name="compiler-warning-level-1-c4382"></a>Compilerwarnung (Stufe 1) C4382

> Auslösen von "*Typ*": ein Typ mit __clrcall-Destruktor oder Kopierkonstruktor kann nur in "/ CLR" abgefangen werden: pure-Modul

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Bei der Kompilierung mit **"/ CLR"** (nicht **/CLR: pure**), Ausnahmebehandlung erwartet, dass die Member-Funktionen in einem systemeigenen Typ sein [__cdecl](../../cpp/cdecl.md) und nicht [__clrcall](../../cpp/clrcall.md). Systemeigene Typen mit Memberfunktionen verwenden `__clrcall` Aufrufkonvention kann nicht abgefangen werden, in einem Modul mit kompiliert **"/ CLR"**.

Wenn in einem Modul kompiliert, die mit die Ausnahme abgefangen wird **/CLR: pure**, können Sie diese Warnung ignorieren.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4382 generiert.

```cpp
// C4382.cpp
// compile with: /clr /W1 /c
struct S {
   __clrcall ~S() {}
};

struct T {
   ~T() {}
};

int main() {
   S s;
   throw s;   // C4382

   S * ps = &s;
   throw ps;   // OK

   T t;
   throw t;   // OK
}
```