---
title: _set_error_mode
ms.date: 11/04/2016
api_name:
- _set_error_mode
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_error_mode
- _set_error_mode
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
ms.openlocfilehash: 15a6d72a79f0498fb7d81094ed3595dea1cf444f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948564"
---
# <a name="_set_error_mode"></a>_set_error_mode

Ändert **__error_mode** , um einen nicht standardmäßigen Speicherort zu bestimmen, an dem die C-Laufzeit eine Fehlermeldung für einen Fehler schreibt, der das Programm beenden könnte.

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

Steuert die Fehlerausgabe Senke, indem der Wert von **__error_mode**festgelegt wird. Beispielsweise können Sie die Ausgabe an einen Standardfehler weiterleiten oder die **MessageBox** -API verwenden.

Der *mode_val* -Parameter kann auf einen der folgenden Werte festgelegt werden.

|Parameter|Beschreibung|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|Die Fehler Senke wird von **__app_type**bestimmt.|
|**_OUT_TO_STDERR**|Fehlersenke ist ein Standardfehler.|
|**_OUT_TO_MSGBOX**|Fehlersenke ist ein Meldungsfeld.|
|**_REPORT_ERRMODE**|Meldet den aktuellen **__error_mode** -Wert.|

Wenn ein anderer Wert als die aufgeführten übergeben wird, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt _set_error_mode **errno** auf **EINVAL** fest und gibt-1 zurück.

Wenn Sie mit einer [Assert](assert-macro-assert-wassert.md)-Anweisung verwendet wird, zeigt **_set_error_mode** die fehlerhafte Anweisung im Dialogfeld an und bietet Ihnen die Möglichkeit, die Schaltfläche **ignorieren** auszuwählen, sodass Sie das Programm weiter ausführen können.

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
