---
title: _set_error_mode
ms.date: 11/04/2016
apiname:
- _set_error_mode
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_error_mode
- _set_error_mode
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
ms.openlocfilehash: 8c95ed45423b791a688f05ea30f48e188826a797
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356648"
---
# <a name="seterrormode"></a>_set_error_mode

Ändert **__error_mode** um einen nicht standardmäßigen Speicherort zu bestimmen, in dem die C-Laufzeit schreibt eine Fehlermeldung für einen Fehler, der das Programm beenden kann.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _set_error_mode(
   int mode_val
);
```

### <a name="parameters"></a>Parameter

*mode_val*<br/>
Ziel der Fehlermeldungen.

## <a name="return-value"></a>Rückgabewert

Gibt die alte Einstellung oder -1 zurück, wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Steuert die fehlerausgabesenke durch Festlegen des Werts der **__error_mode**. Sie können z. B. leiten Sie die Ausgabe in einen Standardfehler oder verwenden Sie die **MessageBox** API.

Die *Mode_val* Parameter kann auf einen der folgenden Werte festgelegt werden.

|Parameter|Beschreibung|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|Fehlersenke richtet sich nach **__app_type**.|
|**_OUT_TO_STDERR**|Fehlersenke ist ein Standardfehler.|
|**_OUT_TO_MSGBOX**|Fehlersenke ist ein Meldungsfeld.|
|**_REPORT_ERRMODE**|Melden Sie den aktuellen **__error_mode** Wert.|

Wenn ein anderer Wert als die aufgeführten übergeben wird, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **_set_error_mode** legt **Errno** zu **EINVAL** und gibt-1 zurück.

Bei Verwendung mit einem [assert](assert-macro-assert-wassert.md), **_set_error_mode** die fehlerhafte Anweisung im Dialogfeld angezeigt, und Ihnen die Möglichkeit der Auswahl der **ignorieren** Schaltfläche können Sie das Programm weiter ausführen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_set_error_mode**|\<stdlib.h>|

## <a name="example"></a>Beispiel

```C
// crt_set_error_mode.c
// compile with: /c
#include <stdlib.h>
#include <assert.h>

int main()
{
   _set_error_mode(_OUT_TO_STDERR);
   assert(2+2==5);
}
```

```Output
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>Siehe auch

[assert Macro, _assert, _wassert](assert-macro-assert-wassert.md)<br/>
