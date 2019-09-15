---
title: _RTC_SetErrorFuncW
ms.date: 11/04/2016
api_name:
- _RTC_SetErrorFuncW
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
ms.openlocfilehash: 0d45e5c857e917ca23b62482c64a06314565226e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948967"
---
# <a name="_rtc_seterrorfuncw"></a>_RTC_SetErrorFuncW

Legt eine Funktion als den Handler für das Melden von Fehlern der Fehlerprüfung zur Laufzeit (RTCs) fest.

## <a name="syntax"></a>Syntax

```C
_RTC_error_fnW _RTC_SetErrorFuncW(
   _RTC_error_fnW function
);
```

### <a name="parameters"></a>Parameter

*Funktion*<br/>
Die Adresse der Funktion, die Fehlerprüfungen zur Laufzeit verarbeitet.

## <a name="return-value"></a>Rückgabewert

Die zuvor definierte Fehlerfunktion. oder **null** , wenn keine zuvor definierte Funktion vorhanden ist.

## <a name="remarks"></a>Hinweise

Verwenden Sie in neuem Code nur **_RTC_SetErrorFuncW**. **_RTC_SetErrorFunc** ist nur aus Gründen der Abwärtskompatibilität in der Bibliothek enthalten.

Der **_RTC_SetErrorFuncW** -Rückruf gilt nur für die Komponente, in der er verknüpft war, aber nicht global.

Stellen Sie sicher, dass die Adresse, die Sie an **_RTC_SetErrorFuncW** übergeben, die einer gültigen Fehler Behandlungs Funktion ist.

Wenn ein Fehler mit [_RTC_SetErrorType](rtc-seterrortype.md)dem Typ-1 zugewiesen wurde, wird die Fehler Behandlungs Funktion nicht aufgerufen.

Bevor Sie diese Funktion aufrufen können, müssen Sie zuerst eine der Initialisierungsfunktionen der Laufzeitfehlerüberprüfung aufrufen. Weitere Informationen finden Sie unter [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).

**_RTC_error_fnW** ist wie folgt definiert:

```cpp
typedef int (__cdecl * _RTC_error_fnW)(
    int errorType,
    const wchar_t * filename,
    int linenumber,
    const wchar_t * moduleName,
    const wchar_t * format,
    ... );
```

Dabei gilt:

*errorType*<br/>
Die Art des Fehlers, der von [_RTC_SetErrorType](rtc-seterrortype.md)angegeben wird.

*filename*<br/>
Die Quelldatei, in der der Fehler aufgetreten ist oder null, wenn keine Debuginformationen verfügbar sind.

*linenumber*<br/>
Die Zeile in *filename* , in der der Fehler aufgetreten ist oder „0“, wenn keine Debuginformationen verfügbar sind.

*moduleName*<br/>
Die DLL oder Name des ausführbaren Programms, wo der Fehler aufgetreten ist.

*format*<br/>
printf-Formatzeichenfolge, um eine Fehlermeldung mit den übrigen Parameter anzuzeigen. Das erste Argument von VA_ARGLIST ist die Fehlernummer des aufgetretenen RTC-Fehlers.

Ein Beispiel für die Verwendung von **_RTC_error_fnW** finden Sie unter [Anpassen der nativen Laufzeitüberprüfung](/visualstudio/debugger/native-run-time-checks-customization).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapi.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)<br/>
