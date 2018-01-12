---
title: ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ctime64_s
- _wctime32_s
- ctime_s
- _wctime64_s
- _ctime32_s
- _wctime_s
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
- ctime64_s
- _ctime32_s
- _tctime32_s
- _ctime64_s
- _wctime_s
- _tctime_s
- _tctime64_s
- ctime_s
- ctime32_s
dev_langs: C++
helpviewer_keywords:
- _wctime32_s function
- ctime64_s function
- _tctime64_s function
- _wctime_s function
- tctime_s function
- _wctime64_s function
- ctime_s function
- ctime32_s function
- _ctime64_s function
- tctime64_s function
- wctime64_s function
- wctime_s function
- _tctime_s function
- tctime32_s function
- wctime32_s function
- time, converting
- _ctime32_s function
- _tctime32_s function
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4a2029db9b38ca1edad0e20764278ec77d205c04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ctimes-ctime32s-ctime64s-wctimes-wctime32s-wctime64s"></a>ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s
Konvertieren Sie einen Zeitwert in eine Zeichenfolge, und passen Sie sie an die Zeitzoneneinstellungen an. Dies sind Versionen von [ctime, _ctime64, _wctime, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) mit Sicherheitserweiterungen, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t ctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _ctime32_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _ctime64_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time64_t *time )  
;  
errno_t _wctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _wctime32_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _wctime64_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time64_t *time   
);  
template <size_t size>  
errno_t _ctime32_s(   
   char (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _ctime64_s(   
   char (&buffer)[size],  
   const __time64_t *time  
); // C++ only  
template <size_t size>  
errno_t _wctime32_s(   
   wchar_t (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _wctime64_s(   
   wchar_t (&buffer)[size],  
   const __time64_t *time   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `buffer`  
 Muss groß genug für 26 Zeichen sein. Ein Zeiger auf das Zeichenfolgenergebnis Zeichen oder `NULL` wenn:  
  
-   `time` ein Datum vor dem 1. Januar 1970 um Mitternacht (koordinierte Weltzeit, UTC) darstellt.  
  
-   Wenn Sie `_ctime32_s` oder `_wctime32_s` verwenden, und `time` ein Datum nach dem 18. Januar 2038, 23:59:59 Uhr (koordinierte Weltzeit, UTC) darstellt.  
  
-   Wenn Sie `_ctime64_s` oder `_wctime64_s` verwenden, und `time` ein Datum nach dem 31. Dezember 3000, 23:59:59 Uhr (koordinierte Weltzeit, UTC) darstellt.  
  
-   Wenn Sie `_ctime_s` oder `_wctime_s` verwenden; diese Funktionen sind Wrapper für die zuvor genannten Funktionen. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 [in] `numberOfElements`  
 Die Größe des Puffers.  
  
 [in] `time`  
 Zeiger auf die gespeicherte Zeit  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich. Wenn ein Fehler aufgrund eines ungültigen Parameters auftritt, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird ein Fehlercode zurückgegeben. Fehlercodes sind in „ERRNO.H“ definiert. Eine Liste dieser Fehler finden Sie unter [errno](../../c-runtime-library/errno-constants.md). Die jeweiligen Fehlercodes, die für jede Fehlerbedingung zurückgegeben werden, sind in folgender Tabelle aufgelistet.  
  
## <a name="error-conditions"></a>Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|`time`|Zurück|Wert in `buffer`.|  
|--------------|------------------------|------------|------------|-----------------------|  
|`NULL`|any|any|`EINVAL`|Nicht geändert|  
|Nicht `NULL` (zeigt auf gültigen Speicher)|0|any|`EINVAL`|Nicht geändert|  
|Nicht `NULL`|0< Größe < 26|any|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL`|>= 26|NULL|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL`|>= 26|< 0|`EINVAL`|Leere Zeichenfolge|  
  
## <a name="remarks"></a>Hinweise  
 Die `ctime_s`-Funktion konvertiert einen als [time_t](../../c-runtime-library/standard-types.md)-Struktur gespeicherten Zeitwert in eine Zeichenfolge. Der `time`-Wert ergibt sich normalerweise aus einem Aufruf von [time](../../c-runtime-library/reference/time-time32-time64.md) und gibt die Anzahl der Sekunden zurück, die seit Mitternacht (00:00:00 Uhr, koordinierte Weltzeit, UTC) am 1. Januar 1970 verstrichen sind. Der Rückgabewert der Zeichenfolge enthält genau 26 Zeichen und sieht so aus:  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 Eine 24-Stunden-Uhr wird verwendet. Alle Felder haben eine feste Breite. Das Zeichen für neue Zeile ('\n') und das Nullzeichen ('\0') nehmen die letzten beiden Stellen der Zeichenfolge ein.  
  
 Die konvertierte Zeichenfolge wird auch gemäß den lokalen Zeitzoneneinstellungen angepasst. Informationen zur Konfiguration der lokalen Zeit finden Sie unter den `time`, [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [localtime32_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)-Funktionen. Informationen zur Definition der Zeitzonenumgebung und der globalen Variablen finden Sie unter der [_tzset](../../c-runtime-library/reference/tzset.md)-Funktion.  
  
 `_wctime32_s` und `_wctime64_s` sind die Breitzeichenversion von `_ctime32_s` und `_ctime64_s` und geben einen Zeiger auf die Breitzeichen-Zeichenfolge zurück. Andernfalls verhalten sich `_ctime64_s`, `_wctime32_s` und `_wctime64_s` identisch zu `_ctime32_s`.  
  
 `ctime_s` ist eine Inlinefunktion, die `_ctime64_s` auswertet, und `time_t` entspricht `__time64_t`. Wenn Sie den Compiler zwingen müssen, `time_t` als das alte 32-Bit- `time_t`zu interpretieren, definieren Sie `_USE_32BIT_TIME_T`. Dadurch wird `ctime_s` mit `_ctime32_s` ausgewertet. Dies ist nicht zu empfehlen, weil bei Ihrer Anwendung nach dem 18. Januar 2038 ein Fehler auftreten kann. Die Verwendung dieses Makros ist auf 64-Bit-Plattformen nicht zulässig.  
  
 Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads (Sichere Vorlagenüberladungen)](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime_s`|`ctime_s`|`ctime_s`|`_wctime_s`|  
|`_tctime32_s`|`_ctime32_s`|`_ctime32_s`|`_wctime32_s`|  
|`_tctime64_s`|`_ctime64_s`|`_ctime64_s`|`_wctime64_s`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`ctime_s`, `_ctime32_s`, `_ctime64_s`|\<time.h>|  
|`_wctime_s`, `_wctime32_s`, `_wctime64_s`|\<time.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_wctime_s.c  
/* This program gets the current  
 * time in time_t form and then uses _wctime_s to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
#define SIZE 26  
  
int main( void )  
{  
   time_t ltime;  
   wchar_t buf[SIZE];  
   errno_t err;  
  
   time( &ltime );  
  
   err = _wctime_s( buf, SIZE, &ltime );  
   if (err != 0)  
   {  
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);  
   }  
   wprintf_s( L"The time is %s\n", buf );  
}  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
The time is Fri Apr 25 13:03:39 2003  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)