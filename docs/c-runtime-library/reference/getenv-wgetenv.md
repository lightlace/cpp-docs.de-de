---
title: getenv, _wgetenv
ms.date: 11/04/2016
api_name:
- getenv
- _wgetenv
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
- api-ms-win-crt-environment-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wgetenv
- getenv
- _tgetenv
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
ms.openlocfilehash: 7cacd8588bcc74c6d064da370ce6254aada56c12
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955061"
---
# <a name="getenv-_wgetenv"></a>getenv, _wgetenv

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

*varname*<br/>
Umgebungsvariablenname.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den Umgebungs Tabelleneintrag zurück, der *varname*enthält. Es ist nicht sicher, der Wert der Umgebungsvariablen mit dem zurückgegebenen Zeiger zu ändern. Verwenden Sie die [_putenv](putenv-wputenv.md) -Funktion, um den Wert einer Umgebungsvariablen zu ändern. Der Rückgabewert ist **null** , wenn *varname* nicht in der Umgebungs Tabelle gefunden wird.

## <a name="remarks"></a>Hinweise

Die **getenv** -Funktion durchsucht die Liste der Umgebungsvariablen nach *varname*. bei **getenv** wird im Windows-Betriebssystem die Groß-/Kleinschreibung nicht beachtet. **getenv** und **_putenv** verwenden die Kopie der Umgebung, auf die die globale Variable **_environ** verweist, um auf die Umgebung zuzugreifen. **getenv** arbeitet nur auf den Datenstrukturen, auf die die Lauf Zeit Bibliothek zugreifen kann, und nicht auf dem Umgebungs Segment, das vom Betriebssystem für den Prozess erstellt wurde. Programme, die das Argument " *TVP* " für [Main](../../cpp/main-program-startup.md) oder [wmain](../../cpp/main-program-startup.md) verwenden, rufen daher möglicherweise ungültige Informationen ab.

Wenn *varname* **null**ist, ruft diese Funktion einen Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion **errno** auf **EINVAL** fest und gibt **null**zurück.

**_wgetenv** ist eine breit Zeichen Version von **getenv**; Das Argument und der Rückgabewert von **_wgetenv** sind Zeichen folgen mit breit Zeichen. Die globale **_wenviron** -Variable ist eine breit Zeichen Version von **_environ**.

In einem MBCS-Programm (z. b. in einem SBCS-ASCII-Programm) ist **_wenviron** anfänglich **null** , da die Umgebung aus Multibyte-Zeichen folgen besteht. Wenn bereits eine (MBCS)-Umgebung vorhanden ist, wird beim ersten [_wputenv](putenv-wputenv.md)oder beim ersten **_wgetenv** -Befehl eine entsprechende breit Zeichen-Zeichen folgen Umgebung erstellt, auf die dann von **_wenviron**verwiesen wird.

Ähnlich in einem Unicode-Programm ( **_wmain**) ist **_environ** anfänglich **null** , da die Umgebung aus Zeichen folgen mit breit Zeichen besteht. Beim ersten Aufrufen von **_putenv**oder beim ersten Aufrufen von **getenv** , wenn bereits eine (Unicode)-Umgebung vorhanden ist, wird eine entsprechende MBCS-Umgebung erstellt, auf die dann von **_environ**verwiesen wird.

Wenn in einem Programm zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden sind, muss das Laufzeitsystem beide Kopien verwalten, wodurch sich die Ausführungszeit verlangsamt. Wenn Sie z. b. **_putenv**aufzurufen, wird auch ein Aufruf von **_wputenv** automatisch ausgeführt, sodass die beiden Umgebungs Zeichenfolgen übereinstimmen.

> [!CAUTION]
> In seltenen Fällen, wenn das Laufzeitsystem sowohl eine Unicodeversion als auch eine Multibyteversion der Umgebung verwaltet, stimmen diese zwei Versionen möglicherweise nicht exakt überein. Dies liegt daran, dass die Zuordnung von einer eindeutigen Unicodezeichenfolge zu einer Multibyte-Zeichenfolge nicht unbedingt eindeutig ist, obwohl sich jede eindeutige Multibyte-Zeichenfolge einer eindeutigen Unicodezeichenfolge zuordnen lässt. Weitere Informationen finden Sie unter [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> Die **_putenv** -und **_getenv** -Funktions Familien sind nicht Thread sicher. **_getenv** könnte einen Zeichen folgen Zeiger zurückgeben, während **_putenv** die Zeichenfolge ändert, was zu zufälligen Fehlern führt. Stellen Sie sicher, dass Aufrufe dieser Funktionen synchronisiert sind.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

Verwenden Sie bei Bedarf **getenv**, **_putenv** und **_tzset** , um den Wert der **TZ** -Umgebungsvariablen zu überprüfen oder zu ändern. Weitere Informationen zu **TZ**finden Sie unter [_tzset](tzset.md) und [_daylight, TimeZone und _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
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
