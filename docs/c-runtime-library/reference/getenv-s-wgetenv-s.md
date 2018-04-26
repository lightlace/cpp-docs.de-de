---
title: getenv_s, _wgetenv_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 42
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 21f0877f2b82f243603dc7fb4edf3eff2bbf4d89
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="getenvs-wgetenvs"></a>getenv_s, _wgetenv_s

Ruft einen Wert aus der aktuellen Umgebung ab. Diese Versionen von [getenv, _wgetenv](getenv-wgetenv.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitserweiterungen im CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
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

### <a name="parameters"></a>Parameter

*pReturnValue*<br/>
Die erforderliche Größe des Puffers, oder 0, wenn die Variable nicht gefunden wird.

*buffer*<br/>
Puffer zum Speichern des Werts der Umgebungsvariablen.

*numberOfElements*<br/>
Größe des *Puffer*.

*Variablenname*<br/>
Umgebungsvariablenname.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, andernfalls ein Fehlercode, wenn ein Fehler auftritt.

### <a name="error-conditions"></a>Fehlerbedingungen

|*pReturnValue*|*buffer*|*numberOfElements*|*Variablenname*|Rückgabewert|
|--------------------|--------------|------------------------|---------------|------------------|
|**NULL**|alle|alle|alle|**EINVAL**|
|alle|**NULL**|>0|alle|**EINVAL**|
|alle|alle|alle|**NULL**|**EINVAL**|

Bei diesen Fehlerbedingungen wird ein Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen die Funktionen **Errno** auf **EINVAL** inventurüberprüfung **EINVAL**.

Auch wenn der Puffer zu klein ist, geben diese Funktionen zurück **ERANGE**. Sie rufen keinen Handler für ungültige Parameter auf. Schreiben sie die erforderliche Puffergröße in *pReturnValue*, und ermöglichen es dadurch Programmen, die Funktion erneut mit einem größeren Puffer aufzurufen.

## <a name="remarks"></a>Hinweise

Die **Getenv_s** -Funktion sucht die Liste von Umgebungsvariablen für *Varname*. **Getenv_s** ist nicht in der Groß-/Kleinschreibung beachtet, in der Windows-Betriebssystem. **Getenv_s** und [_putenv_s](putenv-s-wputenv-s.md) verwenden die Kopie der Umgebung, auf das durch die globale Variable **_environ** auf die Umgebung zuzugreifen. **Getenv_s** arbeitet nur auf den Datenstrukturen, die zur Laufzeit-Bibliothek zugegriffen werden kann und nicht auf die Umgebung "Segment", die vom Betriebssystem für den Prozess erstellt wird. Aus diesem Grund Programme, von denen die *Envp* Argument [main](../../cpp/main-program-startup.md) oder ["wmain"](../../cpp/main-program-startup.md) möglicherweise ungültige Informationen abzurufen.

**_wgetenv_s** ist eine Breitzeichen-Version von **Getenv_s**; der Wert Argument- und Rückgabetypen der **_wgetenv_s** sind Zeichenfolgen mit Breitzeichen. Die **_wenviron** (globale Variable) ist eine Breitzeichen-Version von **_environ**.

In einem MBCS-Programm (z. B. in einem SBCS-ASCII-Programm) **_wenviron** beträgt anfänglich **NULL** , da die Umgebung aus Multibyte-Zeichenfolgen besteht. Klicken Sie dann auf den ersten Aufruf von [_wputenv](putenv-wputenv.md), oder beim ersten Aufruf von **_wgetenv_s**, wenn bereits eine (MBCS)-Umgebung vorhanden ist, wird eine entsprechende Breitzeichen-Umgebung wird erstellt und dann verweist **_wenviron**.

In einem Unicodeprogramm (**_wmain**) Programm **_environ** beträgt anfänglich **NULL** , da die Umgebung der Breitzeichen-Zeichenfolgen besteht. Klicken Sie dann auf den ersten Aufruf von [_putenv](putenv-wputenv.md), oder beim ersten Aufruf von **Getenv_s** Wenn bereits eine (Unicode)-Umgebung vorhanden ist, wird eine entsprechende MBCS-Umgebung wird erstellt und zeigt dann durch **_ Environ**.

Wenn in einem Programm zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden sind, muss das Laufzeitsystem beide Kopien verwalten, wodurch sich die Ausführungszeit verlangsamt. Wenn Sie z. B. Aufrufen **_putenv**, einen Aufruf von **_wputenv** wird ebenfalls automatisch ausgeführt werden, damit die beiden Umgebungszeichenfolgen übereinstimmen.

> [!CAUTION]
> In seltenen Fällen, wenn das Laufzeitsystem sowohl eine Unicodeversion als auch eine Multibyteversion der Umgebung verwaltet, stimmen diese zwei Versionen möglicherweise nicht exakt überein. Dies liegt daran, dass die Zuordnung von einer eindeutigen Unicodezeichenfolge zu einer Multibyte-Zeichenfolge nicht unbedingt eindeutig ist, obwohl sich jede eindeutige Multibyte-Zeichenfolge einer eindeutigen Unicodezeichenfolge zuordnen lässt. Weitere Informationen finden Sie unter [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> Die **_putenv_s** und **_getenv_s** -Funktionsfamilie sind nicht threadsicher. **_getenv_s** gibt möglicherweise einen Zeichenfolgenzeiger beim zurück **_putenv_s** die Zeichenfolge ändert und zufällig generierten Fehlern bewirken. Stellen Sie sicher, dass Aufrufe dieser Funktionen synchronisiert sind.

Die Verwendung dieser Funktionen in C++ wird durch Vorlagenüberladungen vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

Um zu überprüfen oder ändern Sie den Wert, der die **TZ** Umgebung, verwenden **Getenv_s**, **_putenv**, und **_tzset**nach Bedarf. Weitere Informationen zu **TZ**, finden Sie unter [_tzset](tzset.md) und [_daylight, _dstbias, _timezone, und _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**getenv_s**|\<stdlib.h>|
|**_wgetenv_s**|\<stdlib.h> oder \<wchar.h>|

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

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[Umgebungskonstanten](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
