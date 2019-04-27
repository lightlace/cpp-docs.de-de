---
title: Ausnahmen (C/C++)
ms.date: 11/04/2016
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
ms.openlocfilehash: f80b99943b103dcf90c05d59df3169e0e05d79f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271631"
---
# <a name="exceptions-cc"></a>Ausnahmen (C/C++)

Zwei Ausnahmecodes können ausgelöst werden, wenn Fehler auftreten:

- Für eine **LoadLibrary** Fehler

- Für eine **GetProcAddress** Fehler

Hier sind die Ausnahmeinformationen:

```
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

Ausgelösten Ausnahmecodes sind die Standardwerte VcppException (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) und die VcppException (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND)-Werte. Die Ausnahme übergibt einen Zeiger auf eine **DelayLoadInfo** Struktur in der LPDWORD-Wert, der abgerufen werden kann **GetExceptionInformation** in die [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-_exception_record) -Struktur, ExceptionInformation [0]-Feld.

Wenn die falschen Bits im Feld GrAttrs festgelegt sind, wird die Ausnahme darüber hinaus zusätzlich ausgelöst. Diese Ausnahme ist für praktisch, schwerwiegender.

Finden Sie unter [Struktur- und Konstantendefinitionen](structure-and-constant-definitions.md) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung und Benachrichtigung](error-handling-and-notification.md)
