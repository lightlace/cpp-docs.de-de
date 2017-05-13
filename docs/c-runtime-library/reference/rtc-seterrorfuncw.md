---
title: _RTC_SetErrorFuncW | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 9c340310feb94ac181049c01d3ab1efaee2002c3
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW
Legt eine Funktion als den Handler für das Melden von Fehlern der Fehlerprüfung zur Laufzeit (RTCs) fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      _RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW function   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `function`  
 Die Adresse der Funktion, die Fehlerprüfungen zur Laufzeit verarbeitet.  
  
## <a name="return-value"></a>Rückgabewert  
 Die zuvor definierte Fehlerfunktion oder `NULL`, wenn keine zuvor definierte Funktion vorhanden ist.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie in neuem Code ausschließlich `_RTC_SetErrorFuncW`. `_RTC_SetErrorFunc` ist in der Bibliothek nur noch aus Gründen der Abwärtskompatibilität enthalten.  
  
 Der Rückruf `_RTC_SetErrorFuncW` gilt nur für die Komponente, für die er eingebunden wurde, aber nicht global.  
  
 Stellen Sie sicher, dass die Adresse, die Sie an `_RTC_SetErrorFuncW` übergeben, zu einer gültigen Fehlerbehandlungsfunktion gehört.  
  
 Wenn ein Fehler einen Typ "-1" mit zugewiesen wurde [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md), die Fehlerbehandlungsfunktion nicht aufgerufen wird.  
  
 Bevor Sie diese Funktion aufrufen können, müssen Sie zuerst eine der Initialisierungsfunktionen der Laufzeitfehlerüberprüfung aufrufen. Weitere Informationen finden Sie unter [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).  
  
 **_RTC_error_fnW** ist wie folgt definiert:  
  
 **typedef int (__cdecl \*_RTC_error_fnW)(int**  `errorType` **, const wchar_t \*** *filename* **, int**  *linenumber* **, const wchar_t \*** `moduleName` **, const wchar_t \*** *format* **, ...);**  
  
 Dabei gilt:  
  
 `errorType`  
 Die Art des Fehlers, der von [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md)angegeben wird.  
  
 *filename*  
 Die Quelldatei, in der der Fehler aufgetreten ist oder null, wenn keine Debuginformationen verfügbar sind.  
  
 *linenumber*  
 Die Zeile in *filename* , in der der Fehler aufgetreten ist oder „0“, wenn keine Debuginformationen verfügbar sind.  
  
 `moduleName`  
 Die DLL oder Name des ausführbaren Programms, wo der Fehler aufgetreten ist.  
  
 *format*  
 printf-Formatzeichenfolge, um eine Fehlermeldung mit den übrigen Parameter anzuzeigen. Das erste Argument von VA_ARGLIST ist die Fehlernummer des aufgetretenen RTC-Fehlers.  
  
 Ein Beispiel für die Verwendung von **_RTC_error_fnW** finden Sie unter [Anpassen der nativen Laufzeitüberprüfung](/visualstudio/debugger/native-run-time-checks-customization).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)
