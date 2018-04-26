---
title: getenv, _wgetenv | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f83ac7c044f019699556d69ddbf199cbfc02dc0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="getenv-wgetenv"></a>getenv, _wgetenv

Ruft einen Wert aus der aktuellen Umgebung ab. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
char *getenv(
   const char *varname
);
wchar_t *_wgetenv(
   const wchar_t *varname
);
```

### <a name="parameters"></a>Parameter

*Variablenname*<br/>
Umgebungsvariablenname.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die Umgebung Tabelle Eintrag mit *Varname*. Es ist nicht sicher, der Wert der Umgebungsvariablen mit dem zurückgegebenen Zeiger zu ändern. Verwenden der [_putenv](putenv-wputenv.md) Funktion zum Ändern des Werts einer Umgebungsvariablen. Der Rückgabewert ist **NULL** Wenn *Varname* nicht in der umgebungstabelle gefunden wird.

## <a name="remarks"></a>Hinweise

Die **Getenv** -Funktion sucht die Liste von Umgebungsvariablen für *Varname*. **Getenv** ist nicht in der Groß-/Kleinschreibung beachtet, in der Windows-Betriebssystem. **Getenv** und **_putenv** verwenden die Kopie der Umgebung verweist die globale Variable **_environ** auf die Umgebung zuzugreifen. **Getenv** arbeitet nur auf den Datenstrukturen, die auf die Laufzeitbibliothek zugreifen kann und nicht auf die Umgebung "Segment" für den Prozess vom Betriebssystem erstellt wurde. Aus diesem Grund Programme, von denen die *Envp* Argument [main](../../cpp/main-program-startup.md) oder ["wmain"](../../cpp/main-program-startup.md) möglicherweise ungültige Informationen abzurufen.

Wenn *Varname* ist **NULL**, ruft diese Funktion einen Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt **NULL**.

**_wgetenv** ist eine Breitzeichen-Version von **Getenv**; der Wert Argument- und Rückgabetypen der **_wgetenv** sind Zeichenfolgen mit Breitzeichen. Die **_wenviron** (globale Variable) ist eine Breitzeichen-Version von **_environ**.

In einem MBCS-Programm (z. B. in einem SBCS-ASCII-Programm) **_wenviron** beträgt anfänglich **NULL** , da die Umgebung aus Multibyte-Zeichenfolgen besteht. Klicken Sie dann auf den ersten Aufruf von [_wputenv](putenv-wputenv.md), oder beim ersten Aufruf von **_wgetenv** Wenn bereits eine (MBCS)-Umgebung vorhanden ist, wird eine entsprechende Breitzeichen-Umgebung wird erstellt und zeigt dann durch **_wenviron**.

In einem Unicodeprogramm (**_wmain**) Programm **_environ** beträgt anfänglich **NULL** , da die Umgebung der Breitzeichen-Zeichenfolgen besteht. Klicken Sie dann auf den ersten Aufruf von **_putenv**, oder beim ersten Aufruf von **Getenv** Wenn bereits eine (Unicode)-Umgebung vorhanden ist, wird eine entsprechende MBCS-Umgebung wird erstellt und zeigt dann durch **_ Environ**.

Wenn in einem Programm zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden sind, muss das Laufzeitsystem beide Kopien verwalten, wodurch sich die Ausführungszeit verlangsamt. Wenn Sie z. B. Aufrufen **_putenv**, einen Aufruf von **_wputenv** wird ebenfalls automatisch ausgeführt werden, damit die beiden Umgebungszeichenfolgen übereinstimmen.

> [!CAUTION]
> In seltenen Fällen, wenn das Laufzeitsystem sowohl eine Unicodeversion als auch eine Multibyteversion der Umgebung verwaltet, stimmen diese zwei Versionen möglicherweise nicht exakt überein. Dies liegt daran, dass die Zuordnung von einer eindeutigen Unicodezeichenfolge zu einer Multibyte-Zeichenfolge nicht unbedingt eindeutig ist, obwohl sich jede eindeutige Multibyte-Zeichenfolge einer eindeutigen Unicodezeichenfolge zuordnen lässt. Weitere Informationen finden Sie unter [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> Die **_putenv** und **_getenv** -Funktionsfamilie sind nicht threadsicher. **_getenv** gibt möglicherweise einen Zeichenfolgenzeiger beim zurück **_putenv** ist die Zeichenfolge ändert, was zu zufällige Fehlern führt. Stellen Sie sicher, dass Aufrufe dieser Funktionen synchronisiert sind.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

Um zu überprüfen oder ändern Sie den Wert, der die **TZ** Umgebung, verwenden **Getenv**, **_putenv** und **_tzset** nach Bedarf. Weitere Informationen zu **TZ**, finden Sie unter [_tzset](tzset.md) und [_daylight, _timezone und _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**getenv**|\<stdlib.h>|
|**_wgetenv**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
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

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[Umgebungskonstanten](../../c-runtime-library/environmental-constants.md)<br/>
