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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389254"
---
# <a name="fenvaccess"></a>fenv_access
Deaktiviert (**on**) oder aktiviert (**off**) Optimierungen, die die Tests für Flags der Gleitkommaumgbung und Modusänderungen beeinflussen können

## <a name="syntax"></a>Syntax

> **#pragma fenv_access (** { **on** | **off** } **)**

## <a name="remarks"></a>Hinweise

In der Standardeinstellung ist **fenv_access** auf **off** (aus) festgelegt. Wenn der Compiler davon ausgehen kann, dass Ihr Code nicht auf die Gleitkommaumgebung zugreift oder diese manipuliert, können viele Gleitkommaoptimierungen gemacht werden. Legen Sie **fenv_access** auf **on** (an) fest, um dem Compiler mitzuteilen, dass Ihr Code auf die Gleitkommaumgegung zugreift, um Statusflags und Ausnahmen zu testen oder Steuerungsmodusflags festzulegen. Der Compiler deaktiviert diese Optimierungen dann, damit Ihr Code konsistent auf die Gleitkommaumgebung zugreifen kann.

Weitere Informationen zum Gleitkommaverhalten finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](../build/reference/fp-specify-floating-point-behavior.md).

Die Optimierungen, die **fenv_access** unterliegen, sind:

- Globale allgemeine Teilausdruckbeseitigung

- Codebewegung

- Konstantenfaltung

Andere Gleitkommapragmas umfassen:

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>Beispiele

Dieses Beispiel legt **fenv_access** auf **on** fest, um das Gleitkommasteuerregister für die 24-Bit-Genauigkeit festzulegen:

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

Wenn Sie `#pragma fenv_access (on)` aus dem vorherigen Beispiel auskommentieren, können Sie sehen, dass sich die Ausgabe unterscheidet, da der Compiler Kompilierzeitevaluierung anwendet, welche den Kontrollmodus nicht verwendet.

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
