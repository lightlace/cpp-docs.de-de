---
title: fp_contract-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
ms.openlocfilehash: 833d8e7f4b8c9da18901610e52afed619468c5c3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218564"
---
# <a name="fp_contract-pragma"></a>fp_contract-Pragma

Bestimmt, ob eine Gleit Komma Zahl stattfindet. Ein Gleit Komma Wert ist eine Anweisung wie FMA (Fused-multipli-Add), die zwei separate Gleit Komma Operationen zu einer einzigen Anweisung kombiniert. Die Verwendung dieser Anweisungen kann sich auf die Genauigkeit von Gleit Komma Werten auswirken, da der Prozessor nicht nach jedem Vorgang gerundet, sondern nur einmal nach beiden Vorgängen gerundet werden kann.

## <a name="syntax"></a>Syntax

> **#pragma fp_contract (** { **on** | **Off** } **)**

## <a name="remarks"></a>Hinweise

Standardmäßig ist **fp_contract** **auf on**eingestellt. Dies weist den Compiler an, nach Möglichkeit Gleit Komma-Schrumpfungs Anweisungen zu verwenden. Legen Sie **fp_contract** auf **Off** fest, um einzelne Gleit Komma Anweisungen beizubehalten.

Weitere Informationen zum Gleit Komma Verhalten finden Sie unter [/fp (Gleit Komma Verhalten angeben)](../build/reference/fp-specify-floating-point-behavior.md).

Andere Gleitkommapragmas umfassen:

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>Beispiel

Der Code, der aus diesem Beispiel generiert wird, verwendet keine Anweisung mit dem Wert Fused-multiplizieren, auch wenn er auf dem Zielprozessor verfügbar ist. Wenn Sie auskommentieren `#pragma fp_contract (off)`, verwendet der generierte Code ggf. eine Anweisung mit dem Wert Fused-multiplizieren.

```cpp
// pragma_directive_fp_contract.cpp
// on x86 and x64 compile with: /O2 /fp:fast /arch:AVX2
// other platforms compile with: /O2

#include <stdio.h>

// remove the following line to enable FP contractions
#pragma fp_contract (off)

int main() {
   double z, b, t;

   for (int i = 0; i < 10; i++) {
      b = i * 5.5;
      t = i * 56.025;

      z = t * i + b;
      printf("out = %.15e\n", z);
   }
}
```

```Output
out = 0.000000000000000e+00
out = 6.152500000000000e+01
out = 2.351000000000000e+02
out = 5.207249999999999e+02
out = 9.184000000000000e+02
out = 1.428125000000000e+03
out = 2.049900000000000e+03
out = 2.783725000000000e+03
out = 3.629600000000000e+03
out = 4.587525000000000e+03
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
