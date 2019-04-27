---
title: Compilerfehler C2743
ms.date: 11/04/2016
f1_keywords:
- C2743
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
ms.openlocfilehash: 03cd7c13e093be5073b3df7e7cf29dda870bc47a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228929"
---
# <a name="compiler-error-c2743"></a>Compilerfehler C2743

'Typ': Abfangen von nativem Typ mit __clrcall-Destruktor oder Kopierkonstruktor kann nicht

Ein Modul mit kompiliert **"/ CLR"** hat versucht, eine Ausnahme des systemeigenen Typs und, bei denen des Typs der Destruktor oder Kopierkonstruktor verwendet `__clrcall` Aufrufkonvention.

Bei der Kompilierung mit **"/ CLR"**, Behandlung von Ausnahmen erwartet, dass die Member-Funktionen in einem systemeigenen Typ sein [__cdecl](../../cpp/cdecl.md) und nicht [__clrcall](../../cpp/clrcall.md). Systemeigene Typen mit Memberfunktionen verwenden `__clrcall` Aufrufkonvention kann nicht abgefangen werden, in einem Modul mit kompiliert **"/ CLR"**.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2743 generiert.

```
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