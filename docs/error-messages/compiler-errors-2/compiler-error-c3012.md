---
title: Compilerfehler C3012
ms.date: 11/04/2016
f1_keywords:
- C3012
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
ms.openlocfilehash: 9fe0ac7d3637cad3a5571c4631345dac1a0021bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503086"
---
# <a name="compiler-error-c3012"></a>Compilerfehler C3012

> "*systeminterne*": systeminterne Funktion direkt innerhalb eines parallelen Bereichs ist nicht zulässig

Eine [systeminterne Compilerfunktion](../../intrinsics/compiler-intrinsics.md) ist in einem `omp parallel` Bereich nicht zulässig. Um dieses Problem zu beheben, Verschieben von systeminternen Funktionen aus der Region aus, oder durch unspezifischen Entsprechungen ersetzen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3012 generiert und zeigt eine Möglichkeit, das Problem zu beheben:

```cpp
// C3012.cpp
// compile with: /openmp
#ifdef __cplusplus
extern "C" {
#endif
void* _ReturnAddress();
#ifdef __cplusplus
}
#endif

int main()
{
   #pragma omp parallel
   {
      _ReturnAddress();   // C3012
   }
   _ReturnAddress();      // OK
}
```