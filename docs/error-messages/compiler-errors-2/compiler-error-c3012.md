---
title: Compilerfehler C3012 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3012
dev_langs:
- C++
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99bdac5ffb75978479ae7ef420a48b3d1b2f8e64
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063670"
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