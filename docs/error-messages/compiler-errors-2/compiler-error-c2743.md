---
title: Compilerfehler C2743 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4217a1e7a8475362c654ac34b6a345846341ec35
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056487"
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