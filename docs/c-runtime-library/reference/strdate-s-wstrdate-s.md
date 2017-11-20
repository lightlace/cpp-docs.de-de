---
title: _strdate_s, _wstrdate_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdate_s
- _wstrdate_s
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strdate_s
- wstrdate_s
- _wstrdate_s
- strdate_s
- _tstrdate_s
dev_langs: C++
helpviewer_keywords:
- dates, copying
- tstrdate_s function
- wstrdate_s function
- _tstrdate_s function
- strdate_s function
- copying dates
- _strdate_s function
- _wstrdate_s function
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e4d3f6b2b7617705b38c0b8e13ca2ed65fcf8d81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="strdates-wstrdates"></a>_strdate_s, _wstrdate_s
Kopieren des aktuellen Systemdatums in einen Puffer. Dies sind Versionen von [_strdate, _wstrdate](../../c-runtime-library/reference/strdate-wstrdate.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _strdate_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrdate_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strdate_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrdate_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `buffer`  
 Ein Zeiger auf einen Puffer, der mit der formatierten Zeichenfolge ausgefüllt wird.  
  
 [in] `numberOfElements`  
 Größe des Puffers.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in ERRNO.H definiert. Die genauen Fehler, die von der Funktion generiert werden, finden Sie in der folgenden Tabelle. Weitere Informationen zu Fehlercodes finden Sie unter [errno](../../c-runtime-library/errno-constants.md).  
  
## <a name="error-conditions"></a>Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|Zurück|Inhalt von `buffer`|  
|--------------|------------------------|------------|--------------------------|  
|`NULL`|(alle)|`EINVAL`|Nicht geändert|  
|Nicht `NULL` (zeigt auf gültigen Puffer)|0|`EINVAL`|Nicht geändert|  
|Nicht `NULL` (zeigt auf gültigen Puffer)|0 < `numberOfElements` < 9|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL` (zeigt auf gültigen Puffer)|`numberOfElements` >= 9|0|Aktuelles Datum, wie es in den Hinweisen angegeben wurde|  
  
## <a name="security-issues"></a>Sicherheitsprobleme  
 Die Übergabe eines ungültigen Nicht-`NULL`-Werts für den Puffer führt zu einer Zugriffsverletzung, wenn der `numberOfElements`-Parameter größer als 9 ist.  
  
 Die Übergabe von Werten für die Größe, die größer als die tatsächliche Größe von `buffer` ist, führt zu einem Pufferüberlauf.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktionen bieten sicherere Versionen von `_strdate` und `_wstrdate`. Die Funktion `_strdate_s` kopiert das aktuelle Datum in den Puffer, auf den `buffer` zeigt, im Format `mm`/`dd`/`yy`, wobei `mm` zwei Ziffern für den Monat, `dd` zwei Ziffern für den Tag und `yy` die letzten beiden Ziffern des Jahres darstellen. Beispiel: Die Zeichenfolge `12/05/99` stellt das Datum 5. Dezember 1999 dar. Die Zeichenfolge muss mindestens eine Länge von 9 Zeichen aufweisen.  
  
 `_wstrdate_s` ist eine Breitzeichenversion von `_strdate_s`. Das Argument und der Rückgabewert von `_wstrdate_s` sind Zeichenfolgen mit Breitzeichen. Anderenfalls verhalten sich diese Funktionen identisch.  
  
 Wenn `buffer` ein `NULL`-Zeiger oder `numberOfElements` weniger als 9 Zeichen ist, wird der Handler für ungültige Parameter aufgerufen, siehe Beschreibung unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen -1 zurück und legen `errno` auf `EINVAL` fest, wenn der Puffer `NULL` ist oder wenn `numberOfElements` kleiner oder gleich 0, oder legen `errno` auf `ERANGE` fest, wenn `numberOfElements` kleiner als 9 ist.  
  
 In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads (Sichere Vorlagenüberladungen)](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mapping"></a>Zuordnung generischer Textroutinen:  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrdate_s`|`_strdate_s`|`_strdate_s`|`_wstrdate_s`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_strdate`|\<time.h>|  
|`_wstrdate`|\<time.h> oder \<wchar.h>|  
|`_strdate_s`|\<time.h>|  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel hierfür finden Sie unter [time](../../c-runtime-library/reference/time-time32-time64.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)