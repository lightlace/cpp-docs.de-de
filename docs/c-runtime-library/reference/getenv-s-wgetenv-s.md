---
title: getenv_s, _wgetenv_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- getenv_s
- _wgetenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- getenv_s
- _tgetenv_s
- _wgetenv_s
dev_langs:
- C++
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34ba832030e3ad5580dd46deb39c1cbe62738ee9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="getenvs-wgetenvs"></a>getenv_s, _wgetenv_s
Ruft einen Wert aus der aktuellen Umgebung ab. Diese Versionen von [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitserweiterungen im CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [CRT-Funktionen, die in universellen Windows-Plattform-apps nicht unterstützt](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t getenv_s(   
   size_t *pReturnValue,  
   char* buffer,  
   size_t numberOfElements,  
   const char *varname   
);  
errno_t _wgetenv_s(   
   size_t *pReturnValue,  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *varname   
);  
template <size_t size>  
errno_t getenv_s(   
   size_t *pReturnValue,  
   char (&buffer)[size],  
   const char *varname   
); // C++ only  
template <size_t size>  
errno_t _wgetenv_s(   
   size_t *pReturnValue,  
   wchar_t (&buffer)[size],  
   const wchar_t *varname   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `pReturnValue`  
 Die erforderliche Größe des Puffers, oder 0, wenn die Variable nicht gefunden wird.  
  
 `buffer`  
 Puffer zum Speichern des Werts der Umgebungsvariablen.  
  
 `numberOfElements`  
 Größe von `buffer`.  
  
 `varname`  
 Umgebungsvariablenname.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, andernfalls ein Fehlercode, wenn ein Fehler auftritt.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`pReturnValue`|`buffer`|`numberOfElements`|`varname`|Rückgabewert|  
|--------------------|--------------|------------------------|---------------|------------------|  
|`NULL`|any|any|any|`EINVAL`|  
|any|`NULL`|>0|any|`EINVAL`|  
|any|any|any|`NULL`|`EINVAL`|  
  
 Bei diesen Fehlerbedingungen wird ein Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legen die Funktionen `errno` auf `EINVAL` fest und geben `EINVAL` zurück.  
  
 Auch wenn der Puffer zu klein ist, geben diese Funktionen `ERANGE` zurück. Sie rufen keinen Handler für ungültige Parameter auf. Sie geben die erforderliche Puffergröße in `pReturnValue` aus und ermöglichen es dadurch Programmen, die Funktion erneut mit einem größeren Puffer aufzurufen.  
  
## <a name="remarks"></a>Hinweise  
 Die `getenv_s`-Funktion sucht die Liste von Umgebungsvariablen für `varname`. Für `getenv_s` wird im Windows-Betriebssystem die Groß-/Kleinschreibung nicht beachtet. `getenv_s` und `_putenv_s` verwenden die Kopie der Umgebung, auf die die globale Variable `_environ` verweist, um auf die Umgebung zuzugreifen. `getenv_s` arbeitet nur auf den Datenstrukturen, auf die die Laufzeitbibliothek zugreifen kann, und nicht auf dem Umgebungssegment, das vom Betriebssystem für den Prozess erstellt wird. Programme, die das Argument `envp` für [main](../../cpp/main-program-startup.md) oder [wmain](../../cpp/main-program-startup.md) verwenden, rufen daher möglicherweise ungültige Informationen ab.  
  
 `_wgetenv_s` ist eine Breitzeichenversion von `getenv_s`. Das Argument und der Rückgabewert von `_wgetenv_s` sind Zeichenfolgen mit Breitzeichen. Die globale `_wenviron`-Variable ist eine Breitzeichen-Version von `_environ`.  
  
 In einem MBCS-Programm (z. B. in einem SBCS-ASCII-Programm), ist `_wenviron` zunächst `NULL`, da die Umgebung aus den Multibyte-Zeichenfolgen besteht. Beim ersten Aufruf von `_wputenv` oder beim ersten Aufruf von `_wgetenv_s` (sofern bereits eine (MBCS)-Umgebung vorhanden ist), wird dann eine entsprechende Breitzeichenumgebung erstellt, auf die dann `_wenviron` verweist.  
  
 In einem Unicodeprogramm (`(_wmain`) ist `_environ` dementsprechend `NULL`, da die Umgebung aus Zeichenfolgen mit Breitzeichen besteht. Beim ersten Aufruf von `_putenv` oder beim ersten Aufruf von `getenv_s` (sofern bereits eine (Unicode)-Umgebung vorhanden ist), wird dann eine entsprechende MBCS-Umgebung erstellt, auf die dann `_environ` verweist.  
  
 Wenn in einem Programm zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden sind, muss das Laufzeitsystem beide Kopien verwalten, wodurch sich die Ausführungszeit verlangsamt. Beispielsweise erfolgt bei einem Aufruf von `_putenv` automatisch auch ein Aufruf von `_wputenv`, damit die beiden Umgebungszeichenfolgen übereinstimmen.  
  
> [!CAUTION]
>  In seltenen Fällen, wenn das Laufzeitsystem sowohl eine Unicodeversion als auch eine Multibyteversion der Umgebung verwaltet, stimmen diese zwei Versionen möglicherweise nicht exakt überein. Dies liegt daran, dass die Zuordnung von einer eindeutigen Unicodezeichenfolge zu einer Multibyte-Zeichenfolge nicht unbedingt eindeutig ist, obwohl sich jede eindeutige Multibyte-Zeichenfolge einer eindeutigen Unicodezeichenfolge zuordnen lässt. Weitere Informationen finden Sie unter [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Die Familien `_putenv_s` und `_getenv_s` der Funktionen sind nicht threadsicher. `_getenv_s` gibt möglicherweise einen Zeichenfolgenzeiger zurück, während `_putenv_s` die Zeichenfolge ändert, was zu zufälligen Fehlern führen kann. Stellen Sie sicher, dass Aufrufe dieser Funktionen synchronisiert sind.  
  
 Die Verwendung dieser Funktionen in C++ wird durch Vorlagenüberladungen vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tgetenv_s`|`getenv_s`|`getenv_s`|`_wgetenv_s`|  
  
 Um den Wert der Umgebungsvariablen `TZ` zu überprüfen oder zu ändern, verwenden Sie je nach Erfordernis `getenv_s`, `_putenv` und `_tzset`. Weitere Informationen zu `TZ` finden Sie unter [_tzset](../../c-runtime-library/reference/tzset.md) und [_daylight, _timezone und _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`getenv_s`|\<stdlib.h>|  
|`_wgetenv_s`|\<stdlib.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_getenv_s.c  
// This program uses getenv_s to retrieve  
// the LIB environment variable and then uses  
// _putenv to change it to a new value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* libvar;  
   size_t requiredSize;  
  
   getenv_s( &requiredSize, NULL, 0, "LIB");  
   if (requiredSize == 0)  
   {  
      printf("LIB doesn't exist!\n");  
      exit(1);  
   }  
  
   libvar = (char*) malloc(requiredSize * sizeof(char));  
   if (!libvar)  
   {  
      printf("Failed to allocate memory!\n");  
      exit(1);  
   }  
  
   // Get the value of the LIB environment variable.  
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );  
  
   printf( "Original LIB variable is: %s\n", libvar );  
  
   // Attempt to change path. Note that this only affects  
   // the environment variable of the current process. The command  
   // processor's environment is not changed.  
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );  
  
   getenv_s( &requiredSize, NULL, 0, "LIB");  
  
   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));  
   if (!libvar)  
   {  
      printf("Failed to allocate memory!\n");  
      exit(1);  
   }  
  
   // Get the new value of the LIB environment variable.   
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );  
  
   printf( "New LIB variable is: %s\n", libvar );  
  
   free(libvar);  
}  
```  
  
```Output  
Original LIB variable is: c:\vctools\lib;c:\vctools\atlmfc\lib;c:\vctools\PlatformSDK\lib;c:\vctools\Visual Studio SDKs\DIA Sdk\lib;c:\vctools\Visual Studio SDKs\BSC Sdk\lib  
New LIB variable is: c:\mylib;c:\yourlib  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Process and Environment Control (Prozess- und Umgebungssteuerung)](../../c-runtime-library/process-and-environment-control.md)   
 [Umgebungskonstanten](../../c-runtime-library/environmental-constants.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [_dupenv_s, _wdupenv_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md)