---
title: getenv, _wgetenv | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- getenv
- _wgetenv
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
- _wgetenv
- getenv
- _tgetenv
dev_langs:
- C++
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99d9104959dccf4a6879c4e929a1cdc281317171
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="getenv-wgetenv"></a>getenv, _wgetenv
Ruft einen Wert aus der aktuellen Umgebung ab. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [CRT-Funktionen, die in universellen Windows-Plattform-apps nicht unterstützt](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *getenv(   
   const char *varname   
);  
wchar_t *_wgetenv(   
   const wchar_t *varname   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `varname`  
 Umgebungsvariablenname.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Umgebungstabelleneintrag zurück, der `varname` enthält. Es ist nicht sicher, der Wert der Umgebungsvariablen mit dem zurückgegebenen Zeiger zu ändern. Verwenden Sie die Funktion `_putenv`, um den Wert einer Umgebungsvariablen zu ändern. Der Rückgabewert ist `NULL`, wenn `varname` nicht in der Umgebungstabelle gefunden wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `getenv`-Funktion sucht die Liste von Umgebungsvariablen für `varname`. Für `getenv` wird im Windows-Betriebssystem die Groß-/Kleinschreibung nicht beachtet. `getenv` und `_putenv` verwenden die Kopie der Umgebung, auf die die globale Variable `_environ` verweist, um auf die Umgebung zuzugreifen. `getenv` arbeitet nur auf den Datenstrukturen, auf die die Laufzeitbibliothek zugreifen kann, und nicht auf dem Umgebungssegment, das vom Betriebssystem für den Prozess erstellt wurde. Programme, die das Argument `envp` für [main](../../cpp/main-program-startup.md) oder [wmain](../../cpp/main-program-startup.md) verwenden, rufen daher möglicherweise ungültige Informationen ab.  
  
 Wenn `varname` den Wert `NULL` aufweist, ruft diese Funktion einen ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `NULL` zurück.  
  
 `_wgetenv` ist eine Breitzeichenversion von `getenv`. Das Argument und der Rückgabewert von `_wgetenv` sind Zeichenfolgen mit Breitzeichen. Die globale `_wenviron`-Variable ist eine Breitzeichen-Version von `_environ`.  
  
 In einem MBCS-Programm (z. B. in einem SBCS-ASCII-Programm), ist `_wenviron` zunächst `NULL`, da die Umgebung aus den Multibyte-Zeichenfolgen besteht. Beim ersten Aufruf von `_wputenv` oder beim ersten Aufruf von `_wgetenv` (sofern bereits eine (MBCS)-Umgebung vorhanden ist), wird dann eine entsprechende Breitzeichenumgebung erstellt, auf die dann `_wenviron` verweist.  
  
 In einem Unicodeprogramm (`_wmain`) ist `_environ` dementsprechend `NULL`, da die Umgebung aus Zeichenfolgen mit Breitzeichen besteht. Beim ersten Aufruf von `_putenv` oder beim ersten Aufruf von `getenv` (sofern bereits eine (Unicode)-Umgebung vorhanden ist), wird dann eine entsprechende MBCS-Umgebung erstellt, auf die dann `_environ` verweist.  
  
 Wenn in einem Programm zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden sind, muss das Laufzeitsystem beide Kopien verwalten, wodurch sich die Ausführungszeit verlangsamt. Beispielsweise erfolgt bei jedem Aufruf von `_putenv` automatisch auch ein Aufruf von `_wputenv`, damit die beiden Umgebungszeichenfolgen übereinstimmen.  
  
> [!CAUTION]
>  In seltenen Fällen, wenn das Laufzeitsystem sowohl eine Unicodeversion als auch eine Multibyteversion der Umgebung verwaltet, stimmen diese zwei Versionen möglicherweise nicht exakt überein. Dies liegt daran, dass die Zuordnung von einer eindeutigen Unicodezeichenfolge zu einer Multibyte-Zeichenfolge nicht unbedingt eindeutig ist, obwohl sich jede eindeutige Multibyte-Zeichenfolge einer eindeutigen Unicodezeichenfolge zuordnen lässt. Weitere Informationen finden Sie unter [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Die Familien `_putenv` und `_getenv` der Funktionen sind nicht threadsicher. `_getenv` gibt möglicherweise einen Zeichenfolgenzeiger zurück, während `_putenv` die Zeichenfolge ändert, was zu zufälligen Fehlern führen kann. Stellen Sie sicher, dass Aufrufe dieser Funktionen synchronisiert sind.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tgetenv`|`getenv`|`getenv`|`_wgetenv`|  
  
 Um den Wert der Umgebungsvariablen `TZ` zu überprüfen oder zu ändern, verwenden Sie je nach Erfordernis `getenv`, `_putenv` und `_tzset`. Weitere Informationen zu `TZ` finden Sie unter [_tzset](../../c-runtime-library/reference/tzset.md) und [_daylight, _timezone und _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`getenv`|\<stdlib.h>|  
|`_wgetenv`|\<stdlib.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_getenv.c  
// compile with: /W3  
// This program uses getenv to retrieve  
// the LIB environment variable and then uses  
// _putenv to change it to a new value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *libvar;  
  
   // Get the value of the LIB environment variable.  
   libvar = getenv( "LIB" ); // C4996  
   // Note: getenv is deprecated; consider using getenv_s instead  
  
   if( libvar != NULL )  
      printf( "Original LIB variable is: %s\n", libvar );  
  
   // Attempt to change path. Note that this only affects the environment  
   // variable of the current process. The command processor's  
   // environment is not changed.  
   _putenv( "LIB=c:\\mylib;c:\\yourlib" ); // C4996  
   // Note: _putenv is deprecated; consider using putenv_s instead  
  
   // Get new value.  
   libvar = getenv( "LIB" ); // C4996  
  
   if( libvar != NULL )  
      printf( "New LIB variable is: %s\n", libvar );  
}  
```  
  
```Output  
Original LIB variable is: C:\progra~1\devstu~1\vc\lib  
New LIB variable is: c:\mylib;c:\yourlib  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Process and Environment Control (Prozess- und Umgebungssteuerung)](../../c-runtime-library/process-and-environment-control.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [Umgebungskonstanten](../../c-runtime-library/environmental-constants.md)