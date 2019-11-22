---
title: float_control-Pragma
description: Beschreibt die Verwendung und die Auswirkungen der float_control pragma-Direktive. Die float_control-Direktive steuert den Status von präziser Gleit Komma Semantik und Ausnahme Semantik zur Laufzeit.
ms.date: 11/18/2019
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: 0c9caea5ba35a55a53f7b9340cf9bfd2cce80561
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305508"
---
# <a name="float_control-pragma"></a>float_control-Pragma

Gibt Gleitkommaverhalten für eine Funktion an.

## <a name="syntax"></a>Syntax

> **#pragma float_control**\
> **#pragma float_control (präzise,** { **on** | **Off** } [ **, Push** ] **)** \
> **#pragma float_control (außer,** { **on** | **Off** } [ **, Push** ] **)** \
> **#pragma float_control (** { **Push** | **Pop** } **)**

## <a name="options"></a>Optionen

**genauer**, **bei** | **aus** **Push**\
Gibt an, ob eine genaue Gleit Komma Semantik aktiviert (**on**) oder deaktiviert (**Off**) werden soll. Informationen dazu, wie sich diese Option von der **/fp: präzisen** -Compileroption unterscheidet, finden Sie im Abschnitt "Hinweise". Das optionale **pushtoken** weist den Compiler an, die aktuelle Einstellung für **float_control** auf dem internen compilerstapel per Push zu übersetzen.

**mit Ausnahme** **von** |  **Push**\
Gibt an, ob eine Gleit Komma Ausnahme Semantik aktiviert (**on**) oder deaktiviert (**Off**) werden soll. Informationen dazu, wie sich diese Option von der ähnlich benannten **/fp:** -Compileroption unterscheidet, finden Sie im Abschnitt "Hinweise". Das optionale **pushtoken** weist den Compiler an, die aktuelle Einstellung für **float_control** auf dem internen compilerstapel per Push zu übersetzen.

**mit Ausnahme** von kann nur auf **on** festgelegt werden, wenn **präzise** ebenfalls auf **on**festgelegt ist.

**push**\
Überträgt die aktuelle **float_control** -Einstellung auf den internen compilerstapel.

**pop**\
Entfernt die **float_control** Einstellung von der obersten Position des internen Compilerstapels und legt diese die neue **float_control** Einstellung fest.

## <a name="remarks"></a>Hinweise

Die **präzisen** und **außer** Optionen haben nicht das gleiche Verhalten wie die [/FP](../build/reference/fp-specify-floating-point-behavior.md) -Compileroptionen desselben Namens. Das **float_control** -Pragma steuert nur einen Teil des Gleit Komma Verhaltens. Es muss mit [fp_contract](../preprocessor/fp-contract.md) und [fenv_access](../preprocessor/fenv-access.md) -Pragmas kombiniert werden, um die **/FP** -Compileroptionen neu zu erstellen. In der folgenden Tabelle werden die entsprechenden Pragma-Einstellungen für die einzelnen Compileroptionen angezeigt:

| | float_control (präzise, \*) | float_control (außer, \*) | fp_contract (\*) | fenv_access (\*) |
|-|-|-|-|-|
| /fp:strict             | an  | an  | off | an  |
| /fp: strict/fp: außer- | an  | off | off | an  |
| /fp: präzise            | an  | off | an  | off |
| /fp:precise /fp:except | an  | an  | an  | off |
| /fp: schnell               | off | off | an  | off |

Mit anderen Worten, Sie müssen mehrere Pragmas kombinieren, um die Befehlszeilenoptionen " **/fp: fast**", " **/fp: präzise**", " **/fp: strict**" und " **/fp:** " zu emulieren.

Es gibt Einschränkungen hinsichtlich der Art und Weise, wie Sie die **float_control** und **fenv_access** von Gleit Komma-Pragmas verwenden können:

- Sie können **float_control** nur verwenden, um **festzulegen, wenn** **die genaue** Semantik aktiviert ist. Die genaue Semantik kann entweder durch das **float_control** -Pragma oder mithilfe der Compileroptionen **/fp: precise** oder **/fp: strict** aktiviert werden.

- Sie können **float_control** nicht verwenden, um **präzise** zu deaktivieren, wenn die Ausnahme Semantik aktiviert ist, ob durch ein **float_control** -Pragma oder eine **/fp: außer** -Compileroption.

- Sie können **fenv_access** nur aktivieren, wenn eine exakte Semantik aktiviert ist, ob durch ein **float_control** -Pragma oder eine-Compileroption.

- Sie können **float_control** nicht verwenden, um **präzise** zu deaktivieren, wenn **fenv_access** aktiviert ist.

Diese Einschränkungen bedeuten, dass die Reihenfolge einiger Gleit Komma-Pragmas von Bedeutung ist. Verwenden Sie den folgenden Code, um von einem schnellen Modell zu einem Strict-Modell mit dem **float_control** und verwandten Pragmas zu wechseln:

```cpp
#pragma float_control(precise, on)  // enable precise semantics
#pragma fenv_access(on)             // enable environment sensitivity
#pragma float_control(except, on)   // enable exception semantics
#pragma fp_contract(off)            // disable contractions
```

Verwenden Sie den folgenden Code, um von einem Strict-Modell zu einem schnellen Modell mithilfe des **float_control** -Pragmas zu wechseln:

```cpp
#pragma float_control(except, off)  // disable exception semantics
#pragma fenv_access(off)            // disable environment sensitivity
#pragma float_control(precise, off) // disable precise semantics
#pragma fp_contract(on)             // ensable contractions
```

Wenn keine Optionen angegeben sind, hat **float_control** keine Auswirkung.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eine Überlauf Gleit Komma Ausnahme mithilfe der Pragma- **float_control**abgefangen wird.

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

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[fenv_access](../preprocessor/fenv-access.md)\
[fp_contract](../preprocessor/fp-contract.md)
