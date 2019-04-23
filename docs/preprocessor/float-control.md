---
title: float_control
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: 8a7829252cebb726363c67c990a94d08b0d6467a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032309"
---
# <a name="floatcontrol"></a>float_control

Gibt Gleitkommaverhalten für eine Funktion an.

## <a name="syntax"></a>Syntax

> **#pragma Float_control** [ **(** [ *Wert* **,** *Einstellung* [ **, Push** ]] | [ **Push** | **pop** ] **)** ]

## <a name="options"></a>Optionen

*Wert*, *Einstellung* [, **Push**]<br/>
Gibt das Gleitkommaverhalten an. *Wert* kann **präzise**, **strict**, oder **außer**. Weitere Informationen finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](../build/reference/fp-specify-floating-point-behavior.md). Die *Einstellung* Optionen sind möglich **auf** oder **aus**.

Wenn *Wert* ist **strict**, die Einstellungen für **strict** und **außer** angegebenen *Einstellung* . **mit Ausnahme von** kann nur festgelegt werden, um **auf** beim **präzise** oder **strict** nastaven NA hodnotu auch **auf**.

Wenn der optionale **Push** -Token hinzugefügt wird, wird die aktuelle Einstellung für *Wert* wird verschoben, auf dem internen compilerstapel ab.

**push**<br/>
Schieben Sie die aktuelle **Float_control** -Einstellung auf dem internen compilerstapel ab

**pop**<br/>
Entfernt die **Float_control** festlegen, die von der obersten Position des internen Compilerstapels und erstellt die neue **Float_control** festlegen.

## <a name="remarks"></a>Hinweise

Können keine **Float_control** aktivieren **präzise** deaktivieren, wenn **außer** ist. Auf ähnliche Weise **präzise** kann nicht deaktiviert werden Wenn [Fenv_access](../preprocessor/fenv-access.md) ist. Wechseln vom strict-Modell zum fast-Modell mithilfe der **Float_control** Pragma, verwenden Sie den folgenden Code:

```cpp
#pragma float_control(except, off)
#pragma fenv_access(off)
#pragma float_control(precise, off)
```

Wechseln Sie vom fast-Modell zum strict-Modell mit den **Float_control** Pragma, verwenden Sie den folgenden Code:

```cpp
#pragma float_control(precise, on)
#pragma fenv_access(on)
#pragma float_control(except, on)
```

Wenn keine Optionen angegeben sind, **Float_control** hat keine Auswirkungen.

Andere Gleitkommapragmas umfassen:

- [fenv_access](../preprocessor/fenv-access.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie eine Gleitkomma-Stapelüberlauf-Ausnahme abgefangen wird, mithilfe von Pragma **Float_control**.

```cpp
// pragma_directive_float_control.cpp
// compile with: /EHa
#include <stdio.h>
#include <float.h>

double func( ) {
   return 1.1e75;
}

#pragma float_control (except, on)

int main( ) {
   float u[1];
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);
   if (err != 0)
      printf_s("_controlfp_s failed!\n");

   try  {
      u[0] = func();
      printf_s ("Fail");
      return(1);
   }

   catch (...)  {
      printf_s ("Pass");
      return(0);
   }
}
```

```Output
Pass
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
