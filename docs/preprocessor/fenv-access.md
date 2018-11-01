---
title: fenv_access
ms.date: 03/12/2018
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
ms.openlocfilehash: 507e78dd9f9571cc9ce44d7fd91e78b1c955ba73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664034"
---
# <a name="fenvaccess"></a>fenv_access
Deaktiviert (**auf**) oder aktiviert (**aus**) Optimierungen, welche Gleitkommaausnahme zu kennzeichnen, Tests und Modus ändert.

## <a name="syntax"></a>Syntax

> **#pragma fenv_access führen (** { **auf** | **aus** } **)**

## <a name="remarks"></a>Hinweise

In der Standardeinstellung **Fenv_access** ist **aus**. Wenn der Compiler, die davon ausgehen kann Ihren Code nicht zugreifen oder die gleitkommaumgebung bearbeiten, und es viele gleitkommacode Optimierungen durchführen. Legen Sie **Fenv_access** zu **auf** an den Compiler darüber zu informieren, dass Ihr Code die Gleitkommaausnahme-Statusflags, Ausnahmen, zu testen oder Steuerelement Modus-Flags festlegen zugreift. Der Compiler deaktiviert diese Optimierungen, damit Ihr Code die gleitkommaumgebung einheitlich zugreifen kann.

Weitere Informationen zum Gleitkommaverhalten finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](../build/reference/fp-specify-floating-point-behavior.md).

Die Arten von Optimierungen, unterliegen **Fenv_access** sind:

- Globale allgemeine Teilausdruckbeseitigung

- Codebewegung

- Konstantenfaltung

Andere Gleitkommapragmas umfassen:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Beispiele

In diesem Beispiel wird **Fenv_access** zu **auf** gleitkommasteuerelements für die Genauigkeit von 24-Bit-Register festlegen:

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

Wenn Sie auskommentieren `#pragma fenv_access (on)` aus dem vorherigen Beispiel beachten Sie, dass die Ausgabe anders ist, da der Compiler kompilierzeitauswertung, ist das nicht den steuermodus verwendet wird.

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
