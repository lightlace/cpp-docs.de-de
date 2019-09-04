---
title: float_control-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: aa8cdc07953405175c1753791ab53214d73ba516
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218581"
---
# <a name="float_control-pragma"></a>float_control-Pragma

Gibt Gleitkommaverhalten für eine Funktion an.

## <a name="syntax"></a>Syntax

> **#pragma float_control**\
> **#pragma float_control (** { **präzise** | **Strict** | **außer** } **,** { **on** | **Off** } [ **, Push** ] **)** \
> **#pragma float_control (** { **Push** | **Pop** } **)**

## <a name="options"></a>Optionen

**präzise** Strict außer,ein | Push |  | \
Gibt das Gleit Komma Verhalten an, das **präzise**, **streng**oder **außer**sein kann. Weitere Informationen finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](../build/reference/fp-specify-floating-point-behavior.md). Die Einstellung kann entweder ein -oder **ausgeschaltet**werden.

Wenn **Strict**, werden die Einstellungen für " **Strict** " und " **außer** " durch die Einstellung "ein" oder " **aus** " angegeben. **mit Ausnahme** von kann nur auf **on** festgelegt werden, wenn **präzise** oder **Strict** ebenfalls auf **on**festgelegt ist.

Wenn das optionale **pushtoken** hinzugefügt wird, wird die aktuelle Einstellung für **float_control** auf den internen compilerstapel verschoben.

**Push**\
Pushen der aktuellen **float_control** -Einstellung auf den internen compilerstapel

**Chor**\
Entfernt die **float_control** -Einstellung von der obersten Position des internen Compilerstapels und macht diese die neue **float_control** -Einstellung.

## <a name="remarks"></a>Hinweise

Sie können **float_control** nicht verwenden, um **genau** zu deaktivieren, wenn auf on ist. Analog kann nicht deaktiviert werden, wenn [fenv_access](../preprocessor/fenv-access.md) auf ON eingestellt ist. Verwenden Sie den folgenden Code, um vom Strict-Modell zu einem schnellen Modell mit dem **float_control** -Pragma zu wechseln:

```cpp
#pragma float_control(except, off)
#pragma fenv_access(off)
#pragma float_control(precise, off)
```

Verwenden Sie den folgenden Code, um vom fast-Modell zu einem Strict-Modell mit dem **float_control** -Pragma zu wechseln:

```cpp
#pragma float_control(precise, on)
#pragma fenv_access(on)
#pragma float_control(except, on)
```

Wenn keine Optionen angegeben werden, hat **float_control** keine Auswirkung.

Andere Gleitkommapragmas umfassen:

- [fenv_access](../preprocessor/fenv-access.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eine Überlauf Gleit Komma Ausnahme mithilfe von Pragma **float_control**abgefangen wird.

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
