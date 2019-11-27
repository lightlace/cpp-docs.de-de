---
title: Ausnahme Codes beim Laden von DLL-C++Code (C/)
ms.date: 11/19/2019
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
ms.openlocfilehash: f557fe736f45f8c3f5411d076a0be18f1d1b670e
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74243852"
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

Die Ausnahme Codes, die ausgelöst werden, sind die Standardwerte für "VcppException (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND)" und "VcppException" (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND). Die Ausnahme übergibt einen Zeiger auf eine **Delta** -Informationsstruktur im LPDWORD-Wert, der von **GetExceptionInformation** im Feld " [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) Structure, ExceptionInformation [0]" abgerufen werden kann.

Außerdem wird die Ausnahme ERROR_INVALID_PARAMETER ausgelöst, wenn die falschen Bits im Feld grAttrs festgelegt sind. Diese Ausnahme ist für alle Intents und Zwecke schwerwiegend.

Weitere Informationen finden Sie unter [Struktur-und Konstantendefinitionen](structure-and-constant-definitions.md) .

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung und Benachrichtigung](error-handling-and-notification.md)
