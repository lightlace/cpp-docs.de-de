---
title: Compilerfehler C3899
ms.date: 11/04/2016
f1_keywords:
- C3899
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
ms.openlocfilehash: 022bc1a37f7d9cfdb2c206592dd303a9c3c95080
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749112"
---
# <a name="compiler-error-c3899"></a>Compilerfehler C3899

"var": die Verwendung des l-Werts eines initonly-Datenmembers ist nicht direkt innerhalb eines parallelen Bereichs in der Klasse "Class" zulässig.

Ein [initonly-C++Datenmember (/CLI)](../../dotnet/initonly-cpp-cli.md) kann nicht innerhalb dieses Teils eines Konstruktors initialisiert werden, der sich in einem [parallelen](../../parallel/openmp/reference/parallel.md) Bereich befindet.  Dies liegt daran, dass der Compiler eine interne Verschiebung dieses Codes durchführt, sodass er nicht mehr Teil des Konstruktors ist.

Um dies aufzulösen, initialisieren Sie den initonly-Datenmember im Konstruktor, jedoch außerhalb des parallelen Bereichs.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3899 generiert.

```cpp
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
