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
ms.openlocfilehash: cf38af464f08e143ed9073befe30f6aeb8b913b6
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915454"
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

Die Ausnahme Codes, die ausgelöst werden, sind die Standardwerte für "VcppException" (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) und "VcppException" (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND). Die Ausnahme übergibt einen Zeiger auf eine **Delta-loadinfo** -Struktur im LPDWORD-Wert, der von **GetExceptionInformation** im Feld [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-exception_record) Structure, ExceptionInformation [0] abgerufen werden kann.

Außerdem wird die Ausnahme ERROR_INVALID_PARAMETER ausgelöst, wenn die falschen Bits im Feld grAttrs festgelegt sind. Diese Ausnahme ist für alle Intents und Zwecke schwerwiegend.

Weitere Informationen finden Sie unter [Struktur-und Konstantendefinitionen](structure-and-constant-definitions.md) .

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung und Benachrichtigung](error-handling-and-notification.md)
