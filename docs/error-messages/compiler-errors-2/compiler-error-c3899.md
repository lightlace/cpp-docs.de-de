---
title: Compilerfehler C3899 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3899
dev_langs:
- C++
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b154941051e1c6887e8e05756befd6a18c62ed72
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091780"
---
# <a name="compiler-error-c3899"></a>Compilerfehler C3899

'Var': Verwendung l-Wertes eines Initonly-Datenmembers ist direkt innerhalb eines parallelen Bereichs in der Klasse "Klasse" nicht zulässig.

Ein [Initonly (C++ / CLI)](../../dotnet/initonly-cpp-cli.md) -Datenmember kann nicht initialisiert werden, in dieser Teil einen Konstruktor, der in einem [parallele](../../parallel/openmp/reference/parallel.md) Region.  Dies ist, da der Compiler eine interne Verschieben von Code ist so, dass es tatsächlich nicht mehr Teil des Konstruktors ist.

Um zu beheben, initialisieren Sie Initonly-Datenmembers im Konstruktor, aber außerhalb des parallelen Bereichs ein.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3899 generiert.

```
// C3899.cpp
// compile with: /clr /openmp
#include <omp.h>

public ref struct R {
   initonly int x;
   R() {
      x = omp_get_thread_num() + 1000;   // OK
      #pragma omp parallel num_threads(5)
      {
         // cannot assign to 'x' here
         x = omp_get_thread_num() + 1000;   // C3899
         System::Console::WriteLine("thread {0}", omp_get_thread_num());
      }
      x = omp_get_thread_num() + 1000;   // OK
   }
};

int main() {
   R^ r = gcnew R;
   System::Console::WriteLine(r->x);
}
```