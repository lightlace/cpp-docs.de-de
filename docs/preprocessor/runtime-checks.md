---
title: runtime_checks-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
ms.openlocfilehash: a1c8e6cca27e157818e6ec80182f8fefa112daf1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216617"
---
# <a name="runtime_checks-pragma"></a>runtime_checks-Pragma

Dient der Deaktivierung oder Wiederherstellung der [/RTC](../build/reference/rtc-run-time-error-checks.md) -Einstellungen.

## <a name="syntax"></a>Syntax

> **#pragma runtime_checks ("** [ *runtime_checks* ] **",** { **Restore** | **Off** } **)**

## <a name="remarks"></a>Hinweise

Sie können keine Lauf Zeit Überprüfung aktivieren, die nicht durch eine-Compileroption aktiviert wurde. Wenn Sie z. b. nicht `/RTCs` in der Befehlszeile angeben, `#pragma runtime_checks( "s", restore)` wird durch die Angabe von keine Stapel Rahmen Überprüfung aktiviert.

Das **runtime_checks** -Pragma muss außerhalb einer Funktion erscheinen und wird bei der ersten Funktion wirksam, die nach dem Betrachten des Pragmas definiert ist. Die Argumente **restore** und **off** schalten die in **runtime_checks** angegebenen Optionen ein oder aus.

Die Option **runtime_checks** kann leer sein oder mehrere Parameter aus der folgenden Tabelle enthalten.

### <a name="parameters-of-the-runtime_checks-pragma"></a>Parameter des runtime_checks-Pragmas

| Parameter | Typ der Laufzeitüberprüfung |
|--------------------|-----------------------------|
| **s** | Aktiviert die Überprüfung des Stapels (Frames). |
| **c** | Meldet die Zuweisung eines Werts zu einem kleineren Datentyp, der zu einem Datenverlust führt. |
| **n** | Meldet, wenn eine Variable verwendet wird, bevor Sie definiert wird. |

Dabei handelt es sich um dieselben Parameter, die `/RTC` mit der-Compileroption verwendet werden. Beispiel:

```cpp
#pragma runtime_checks( "sc", restore )
```

Verwenden des **runtime_checks** -Pragmas mit einer leeren Zeichenfolge ( **""** ) ist eine besondere Form der Direktive:

- Wenn Sie den **Off** -Parameter verwenden, werden die in der obigen Tabelle aufgeführten Lauf Zeit Fehlerüberprüfungen deaktiviert.

- Wenn Sie den **Restore** -Parameter verwenden, setzt er die Lauf Zeit Fehlerüberprüfungen auf die mit der `/RTC` -Compileroption angegebenen Einstellungen zurück.

```cpp
#pragma runtime_checks( "", off )
/* runtime checks are off in this region */
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
