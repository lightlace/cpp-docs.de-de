---
title: Fenv_access | Microsoft Docs
ms.custom: ''
ms.date: 03/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2f6f379e61ea84c1142bd94be49b55a50b28753
ms.sourcegitcommit: 1ac8f983eeaacd09135a249dea00f10e1c94e0e3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36963322"
---
# <a name="fenvaccess"></a>fenv_access

Deaktiviert (**auf**) oder aktiviert (**deaktiviert**) Optimierungen, mit denen gleitkommaumgebung zu ändern, könnte zu kennzeichnen, Tests und den Modus geändert hat.

## <a name="syntax"></a>Syntax

> **#pragma Fenv_access (** { **auf** | **deaktiviert** } **)**  

## <a name="remarks"></a>Hinweise

Standardmäßig **Fenv_access** ist **deaktiviert**. Wenn der Compiler, die voraussichtlich Code nicht zugreifen oder gleitkommaumgebung zu bearbeiten, dann können sie viele gleitkommacode Optimierungen durchführen. Legen Sie **Fenv_access** auf **auf** dem Compiler informiert, dass Ihr Code gleitkommaumgebung Statusflags, Ausnahmen, testen oder Steuerelement Modus Flags festgelegt zugreift. Der Compiler wird diese Optimierungen deaktiviert, sodass der Code konsistent gleitkommaumgebung zugreifen kann. 

Weitere Informationen zu Gleitkommaverhalten, finden Sie unter [/fp (Festlegen von Floating-Verhalten)](../build/reference/fp-specify-floating-point-behavior.md).

Die Arten von Optimierungen, mit denen unterliegen **Fenv_access** sind:

- Globale allgemeine Teilausdruckbeseitigung

- Codebewegung

- Konstantenfaltung

Andere Gleitkommapragmas umfassen:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Beispiele

In diesem Beispiel wird **Fenv_access** auf **auf** gleitkommasteuerelements Register für das 24-Bit-Präzision festlegen:

```cpp
// pragma_directive_fenv_access_x86.cpp
// compile with: /O2
// processor: x86
#include <stdio.h>
#include <float.h>
#include <errno.h>
#pragma fenv_access (on)

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=9.999999776482582e-003
```

Wenn Sie auskommentieren `#pragma fenv_access (on)` aus dem vorherigen Beispiel beachten Sie, dass die Ausgabe anders ist, da der Compiler eine kompilierzeitauswertung, die nicht den steuermodus verwendet vornimmt.

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2
#include <stdio.h>
#include <float.h>

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=1.000000000000000e-002
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
