---
title: Fp_contract | Microsoft-Dokumentation
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
ms.openlocfilehash: 95f23fa132a263970047a480ccde37382b6d03de
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052163"
---
# <a name="fpcontract"></a>fp_contract

Bestimmt, ob ein Gleitkommawert-Kontraktion stattfindet. Eine Gleitkommawert-Kontraktion ist eine Anweisung wie z. B. FMA (Fused-Multiply-Add), die zwei separate Vorgänge mit Gleitkommas in eine einzelne Anweisung kombiniert werden. Mithilfe dieser Anweisungen kann Genauigkeit von Gleitkommawerten, beeinträchtigen, da anstelle von Rundung nach jedem Vorgang, der Prozessor nur einmal nach beide Vorgänge möglicherweise rundet.

## <a name="syntax"></a>Syntax

> **#pragma Fp_contract (** { **auf** | **aus** } **)**

## <a name="remarks"></a>Hinweise

In der Standardeinstellung **Fp_contract** ist **auf**. Dies weist den Compiler an Gleitkommawert-Kontraktion Anweisungen möglichst verwenden. Legen Sie **Fp_contract** zu **aus** um einzelne Gleitkommahardware-Anweisungen zu erhalten.

Weitere Informationen zum Gleitkommaverhalten finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](../build/reference/fp-specify-floating-point-behavior.md).

Andere Gleitkommapragmas umfassen:

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>Beispiel

Aus diesem Beispiel generierte Code wird eine fused-multiply-add-Anweisung nicht verwendet, auch wenn es auf dem Zielprozessor verfügbar ist. Wenn Sie auskommentieren `#pragma fp_contract (off)`, der generierte Code kann eine fused-multiply-add-Anweisung verwenden, sofern diese verfügbar ist.

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
