---
title: asctime_s, _wasctime_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wasctime_s
- asctime_s
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
- asctime_s
- _wasctime_s
- _tasctime_s
dev_langs:
- C++
helpviewer_keywords:
- tasctime_s function
- _tasctime_s function
- time structure conversion
- wasctime_s function
- time, converting
- _wasctime_s function
- asctime_s function
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
caps.latest.revision: 29
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 4d4b2bf3c4fb4180b6da1d39ca26bfe819971f31
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="asctimes-wasctimes"></a>asctime_s, _wasctime_s
Konvertieren Sie eine `tm`-Zeitstruktur in einer Zeichenfolge. Diese Funktionen sind Versionen von [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen](../../c-runtime-library/security-features-in-the-crt.md) in der CRT beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t asctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const struct tm *_tm   
);  
errno_t _wasctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements  
   const struct tm *_tm   
);  
template <size_t size>  
errno_t asctime_s(   
   char (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
template <size_t size>  
errno_t _wasctime_s(   
   wchar_t (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 [out] Ein Zeiger auf einen Puffer, um Zeichenfolgenergebnis zu speichern. Diese Funktion nimmt einen Zeiger an einem gültigen Speicherort mit einer von `numberOfElements` angegebenen Größe an.  
  
 `numberOfElements`  
 [in] Die Größe des Puffers, die verwendet wird, um das Ergebnis zu speichern.  
  
 `_tm`  
 [in] Zeit-/Datumsstruktur. Diese Funktion nimmt einen Zeiger auf ein gültiges `struct tm`-Objekt an.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich. Wenn es einen Fehler gibt, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, ist der Rückgabewert ein Fehlercode. Fehlercodes sind in ERRNO.H definiert. Weitere Informationen finden Sie unter [errno-Konstanten](../../c-runtime-library/errno-constants.md). Die jeweiligen Fehlercodes, die für jede Fehlerbedingung zurückgegeben werden, sind in folgender Tabelle aufgelistet.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|`tm`|Zurück|Wert in `buffer`|  
|--------------|------------------------|----------|------------|-----------------------|  
|`NULL`|Beliebig|Beliebig|`EINVAL`|Nicht geändert|  
|Nicht `NULL` (zeigt auf gültigen Speicher)|0|Beliebig|`EINVAL`|Nicht modifiziert|  
|Nicht `NULL`|0<Größe<26|Beliebig|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL`|>= 26|`NULL`|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL`|>= 26|Ungültige Zeitstruktur oder Zeitkomponentenwerte außerhalb des Bereichs|`EINVAL`|Leere Zeichenfolge|  
  
> [!NOTE]
>  Fehlerbedingungen für `wasctime_s` ähneln denen für `asctime_s`. Der einzige Unterschied ist, dass die Größenbeschränkung in Wörtern angegeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `asctime`-Funktion konvertiert eine als Struktur gespeicherte Zeit in eine Zeichenfolge. Der `_tm`-Wert wird normalerweise durch einen Aufruf von `gmtime` oder `localtime` abgerufen. Beide Funktionen können verwenden werden, um eine `tm`-Struktur wie in TIME.H definiert auszufüllen.  
  
|timeptr.member|Wert|  
|--------------------|-----------|  
|`tm_hour`|Stunden seit Mitternacht (0-23)|  
|`tm_isdst`|Positiv bei Sommerzeit; 0 bei Winterzeit; negativ bei unbekannter Zeit. Die C-Laufzeitbibliothek wendet die Regeln der Vereinigten Staaten an, um die Berechnung der Sommerzeit (DST, Daylight Saving Time) zu implementieren.|  
|`tm_mday`|Tag des Monats (1-31)|  
|`tm_min`|Minuten nach Stunde (0-59)|  
|`tm_mon`|Monat (0-11; Januar = 0)|  
|`tm_sec`|Sekunden nach Minute (0-59)|  
|`tm_wday`|Tag der Woche (0-6; Sonntag = 0)|  
|`tm_yday`|Tag des Jahres (0-365; 1. Januar = 0)|  
|`tm_year`|Jahr (aktuelles Jahr minus 1900)|  
  
 Die konvertierte Zeichenfolge wird auch gemäß den lokalen Zeitzoneneinstellungen angepasst. Informationen zur Konfiguration der Zeitzonen finden Sie unter den [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md), [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [localtime_s, _localtime32_s, _localtime64_2](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)-Funktionen. Informationen zur Definition der Zeitzonenumgebung und globalen Variablen finden Sie unter der [_tzset](../../c-runtime-library/reference/tzset.md)-Funktion.  
  
 Das von `asctime_s` erstellte Zeichenfolgeergebnis enthält genau 26 Zeichen und sieht so aus: `Wed Jan 02 02:03:55 1980\n\0`. Eine 24-Stunden-Uhr wird verwendet. Alle Felder haben eine feste Breite. Die Zeilenwechsel- und Nullzeichen nehmen die letzten beiden Stellen der Zeichenfolge ein. Der Wert, der als zweiter Parameter übergeben wird, sollte mindestens so hoch sein. Wenn er niedriger ist, wird ein Errorcode (`EINVAL`) zurückgegeben.  
  
 `_wasctime_s` ist eine Breitzeichenversion von `asctime_s`. `_wasctime_s` und `asctime_s` verhalten sich andernfalls identisch.  
  
### <a name="generic-text-routine-mapping"></a>Routinemäßige Allgemeintext-Zuordnung  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tasctime_s`|`asctime_s`|`asctime_s`|`_wasctime_s`|  
  
 Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladung](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`asctime_s`|\<time.h>|  
|`_wasctime_s`|\<time.h> oder \<wchar.h>|  
  
## <a name="security"></a>Sicherheit  
 Wenn der Zeiger auf den Puffer nicht `NULL` ist, und der Zeiger nicht auf einen gültigen Puffer zeigt, überschreibt die Funktion das, was sich dort befindet. Dies kann auch zu einer Zugriffsverletzung führen.  
  
 Wenn das übergebene Größenargument größer als die tatsächliche Puffergröße ist, kann ein [Pufferüberlauf](http://msdn.microsoft.com/library/windows/desktop/ms717795) auftreten.  
  
## <a name="example"></a>Beispiel  
 Dieses Programm platziert die Systemzeit in ein längeres, ganzzahliges `aclock`, übersetzt sie in die Struktur `newtime` und konvertiert sie dann mithilfe der `asctime_s`-Funktion in eine Zeichenfolgeform für die Ausgabe.  
  
```  
// crt_asctime_s.c  
#include <time.h>  
#include <stdio.h>  
  
struct tm newtime;  
__time32_t aclock;  
  
int main( void )  
{  
   char buffer[32];  
   errno_t errNum;  
   _time32( &aclock );   // Get time in seconds.  
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.  
  
   // Print local time as a string.  
  
   errNum = asctime_s(buffer, 32, &newtime);  
   if (errNum)  
   {  
       printf("Error code: %d", (int)errNum);  
       return 1;  
   }  
   printf( "Current date and time: %s", buffer );  
   return 0;  
}  
```  
  
```Output  
Current date and time: Wed May 14 15:30:17 2003  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
