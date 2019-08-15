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
ms.openlocfilehash: 360acba73278902cc40d10fd975011488742a7a2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492930"
---
# <a name="exceptions-cc"></a>Ausnahmen (C/C++)

Wenn Fehler auftreten, können zwei Ausnahme Codes ausgelöst werden:

- Bei einem **LoadLibrary** -Fehler

- Bei einem **GetProcAddress** -Fehler

Dies sind die Ausnahme Informationen:

```
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

Die Ausnahme Codes, die ausgelöst werden, sind die Standardwerte für "VcppException" (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) und "VcppException" (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND). Die Ausnahme übergibt einen Zeiger auf eine **Delta-loadinfo** -Struktur im LPDWORD-Wert, der von **GetExceptionInformation** im Feld [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) Structure, ExceptionInformation [0] abgerufen werden kann.

Außerdem wird die Ausnahme ERROR_INVALID_PARAMETER ausgelöst, wenn die falschen Bits im Feld grAttrs festgelegt sind. Diese Ausnahme ist für alle Intents und Zwecke schwerwiegend.

Weitere Informationen finden Sie unter [Struktur-und Konstantendefinitionen](structure-and-constant-definitions.md) .

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung und Benachrichtigung](error-handling-and-notification.md)
