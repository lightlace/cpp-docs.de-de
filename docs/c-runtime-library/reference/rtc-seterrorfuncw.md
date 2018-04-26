---
title: _RTC_SetErrorFuncW | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _RTC_SetErrorFuncW
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
apitype: DLLExport
f1_keywords:
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1eb3b8e5f6fb602675538c6588372b87df8781ac
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW

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

Die zuvor definierte Fehlerfunktion; oder **NULL** , wenn keine zuvor definierte Funktion vorhanden ist.

## <a name="remarks"></a>Hinweise

Verwenden Sie in neuem Code ausschließlich **_RTC_SetErrorFuncW**. **_RTC_SetErrorFunc** nur in der Bibliothek aus Gründen der Abwärtskompatibilität enthalten ist.

Die **_RTC_SetErrorFuncW** Rückruf gilt nur für die Komponente, die er eingebunden wurde aber nicht global.

Stellen Sie sicher, dass die Adresse, die Sie zum übergeben **_RTC_SetErrorFuncW** ist, die von einer gültigen Fehlerbehandlungsfunktion gehört.

Wenn ein Fehler einen Typ "-1" mit zugewiesen wurde [_RTC_SetErrorType](rtc-seterrortype.md), die Fehlerbehandlungsfunktion nicht aufgerufen wird.

Bevor Sie diese Funktion aufrufen können, müssen Sie zuerst eine der Initialisierungsfunktionen der Laufzeitfehlerüberprüfung aufrufen. Weitere Informationen finden Sie unter [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).

**_RTC_error_fnW** ist wie folgt definiert:

> **TypeDef-Int (__cdecl \*_RTC_error_fnW) (Int** *ErrorType* **, const Wchar_t \***  *Filename* **, Int***Linenumber* **, const Wchar_t \***  *"ModuleName"* **, const Wchar_t \***  *Format* **,...);** 

Dabei gilt:

*ErrorType* den Typ des Fehlers, der angegebenen [_RTC_SetErrorType](rtc-seterrortype.md).

*FileName* der Quelldatei, in dem der Fehler aufgetreten ist, oder Null, wenn keine Debuginformationen verfügbar sind.

*LineNumber* der Zeile im *Filename* , in dem der Fehler aufgetreten ist, oder 0, wenn keine Debuginformationen verfügbar sind.

*"ModuleName"* die DLL oder Name der ausführbaren Datei, in dem der Fehler aufgetreten ist.

*Format* Printf-Formatzeichenfolge, um eine Fehlermeldung, die mit den übrigen Parameter anzuzeigen. Das erste Argument von VA_ARGLIST ist die Fehlernummer des aufgetretenen RTC-Fehlers.

Ein Beispiel für die Verwendung von **_RTC_error_fnW** finden Sie unter [Anpassen der nativen Laufzeitüberprüfung](/visualstudio/debugger/native-run-time-checks-customization).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapi.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)<br/>
