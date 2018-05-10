---
title: Fp_contract | Microsoft Docs
ms.custom: ''
ms.date: 03/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 514b4708129d625ea7880e4c61be22c4b1ac2db5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="fpcontract"></a>fp_contract

Bestimmt, ob Gleitkommawert-Kontraktion stattfindet. Ein Gleitkommawert-Kontraktion ist eine Anweisung wie z. B. FMA (Fused Multiply-Add), die zwei separate Gleitkommaoperationen in eine einzelne Anweisung kombiniert. Verwendung von diesen Anweisungen kann Gleitkommazahlen mit einfacher Genauigkeit, beeinträchtigen, da es sich bei statt Rundung nach jedem Vorgang, der Prozessor nur einmal nach beide Vorgänge runden kann.

## <a name="syntax"></a>Syntax

> **#pragma Fp_contract (** { **auf** | **deaktiviert** } **)**  

## <a name="remarks"></a>Hinweise  

Standardmäßig **Fp_contract** ist **auf**. Das weist den Compiler an, verwenden Sie möglichst Gleitkommawert-Kontraktion-Anweisungen. Legen Sie **Fp_contract** auf **deaktiviert** einzelne Gleitkommazahl Anweisungen erhalten bleiben.

Weitere Informationen zu Gleitkommaverhalten, finden Sie unter [/fp (Festlegen von Floating-Verhalten)](../build/reference/fp-specify-floating-point-behavior.md).

Andere Gleitkommapragmas umfassen:

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>Beispiel

Aus diesem Beispiel generierte Code verwendet eine fused multiply-add-Anweisung nicht, auch wenn es auf dem Zielprozessor verfügbar ist. Wenn Sie auskommentieren `#pragma fp_contract (off)`, der generierte Code möglicherweise eine fused multiply-add-Anweisung verwenden, sofern dieser verfügbar ist.  
  
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
