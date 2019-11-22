---
title: fenv_access-Pragma
description: Beschreibt die Verwendung und die Auswirkungen der fenv_access Pragma-Direktive. Die fenv_access-Direktive steuert den Zugriff auf die Gleit Komma Umgebung zur Laufzeit.
ms.date: 11/19/2019
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
ms.openlocfilehash: e03eb404f2805a4f7c96509600c063c1b1acf629
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305852"
---
# <a name="fenv_access-pragma"></a>fenv_access-Pragma

Deaktiviert (**on**) oder aktiviert (**off**) Optimierungen, die die Tests für Flags der Gleitkommaumgbung und Modusänderungen beeinflussen können

## <a name="syntax"></a>Syntax

> **#pragma fenv_access (** { **on** | **off** } **)**

## <a name="remarks"></a>Hinweise

In der Standardeinstellung ist **fenv_access** auf **off** (aus) festgelegt. Der Compiler geht davon aus, dass der Code nicht auf die Gleit Komma Umgebung zugreift oder Sie bearbeitet. Wenn der Zugriff auf die Umgebung nicht erforderlich ist, kann der Compiler mehr erreichen, um den Gleit Komma Code zu optimieren.

Aktivieren Sie **fenv_access** , wenn der Code Gleit Komma-Statusflags oder-Ausnahmen testet oder steuerungsmodusflags festlegt. Der Compiler deaktiviert Gleit Komma Optimierungen, sodass der Code konsistent auf die Gleit Komma Umgebung zugreifen kann.

Die Befehlszeilenoption [/FP: strict] aktiviert **fenv_access**automatisch. Weitere Informationen zu diesem und anderen Gleit Komma Verhalten finden Sie unter [/fp (Gleit Komma Verhalten angeben)](../build/reference/fp-specify-floating-point-behavior.md).

Es gibt Einschränkungen hinsichtlich der Art und Weise, wie Sie das **fenv_access** -Pragma in Kombination mit anderen Gleit Komma Einstellungen verwenden können:

- Sie können **fenv_access** nur aktivieren, wenn die genaue Semantik aktiviert ist. Die genaue Semantik kann entweder durch das [float_control](float-control.md) -Pragma oder mithilfe der Compileroptionen [/fp: precise](../build/reference/fp-specify-floating-point-behavior.md) oder [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) aktiviert werden. Der Compiler ist standardmäßig auf **/fp: precise** festgelegt, wenn keine andere Gleit Komma-Befehlszeilenoption angegeben wird.

- Sie können **float_control** nicht verwenden, um die genaue Semantik zu deaktivieren, wenn **fenv_access (on)** festgelegt ist.

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
// compile with: /O2 /arch:IA32
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
out=9.999999776482582e-03
```

Wenn Sie `#pragma fenv_access (on)` aus dem vorherigen Beispiel kommentieren, ist die Ausgabe anders. Der Grund hierfür ist, dass der Compiler eine Kompilierzeit Auswertung durchführt, die den Steuerelement Modus nicht verwendet.

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2 /arch:IA32
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
out=1.000000000000000e-02
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
