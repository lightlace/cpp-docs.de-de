---
title: _searchenv, _wsearchenv
ms.date: 11/04/2016
api_name:
- _searchenv
- _wsearchenv
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
- _wsearchenv
- _tsearchenv
- wsearchenv
- _searchenv
- searchenv
helpviewer_keywords:
- _wsearchenv function
- files [C++], finding
- _searchenv function
- tsearchenv function
- environment paths, searching for files
- _tsearchenv function
- wsearchenv function
- searchenv function
- environment paths
ms.assetid: 9c944a27-d326-409b-aee6-410e8762d9d3
ms.openlocfilehash: a3139ab87335ba581ef65707602c5da1819ce4a1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948775"
---
# <a name="_searchenv-_wsearchenv"></a>_searchenv, _wsearchenv

Verwendet Umgebungspfade für die Suche nach einer Datei. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md).

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
void _searchenv(
   const char *filename,
   const char *varname,
   char *pathname
);
void _wsearchenv(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname
);
template <size_t size>
void _searchenv(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
void _wsearchenv(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t (&pathname)[size]
); // C++ only
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Der Name der zu suchenden Datei.

*varname*<br/>
Zu durchsuchende Umgebung.

*Pfadnamen*<br/>
Puffer zum Speichern des vollständigen Pfades.

## <a name="remarks"></a>Hinweise

Die **_searchenv** -Routine sucht in der angegebenen Domäne nach der Zieldatei. Die *varname* -Variable kann eine beliebige Umgebung oder eine benutzerdefinierte Variable sein – z. b. **path**, **lib**oder **include**–, die eine Liste von Verzeichnis Pfaden angibt. Da bei **_searchenv** die Groß-/Kleinschreibung beachtet wird, sollte *varname* dem Fall der Umgebungsvariablen entsprechen.

Die Routine sucht zuerst im aktuellen Arbeitsverzeichnis nach der Datei. Wenn die Datei dort nicht gefunden wird, werden die in der Umgebungsvariablen angegebenen Verzeichnisse durchsucht. Wenn sich die Zieldatei in einem dieser Verzeichnisse befindet, wird der neu erstellte Pfad in *Pfadnamen*kopiert. Wenn die Datei *Namen* Datei nicht gefunden wird, enthält *Pfadnamen* eine leere NULL-terminierte Zeichenfolge.

Der *Pfadname* -Puffer muss mindestens **_MAX_PATH** Zeichen lang sein, um die vollständige Länge des erstellten Pfadnamens zu berücksichtigen. Andernfalls kann **_searchenv** den *Pfadnamen* -Puffer überlaufen und ein unerwartetes Verhalten verursachen.

**_wsearchenv** ist eine breit Zeichen Version von **_searchenv**, und die Argumente für **_wsearchenv** sind Zeichen folgen mit breit Zeichen. **_wsearchenv** und **_searchenv** Verhalten sich andernfalls identisch.

Wenn *filename* eine leere Zeichenfolge ist, geben diese Funktionen **ENOENT**zurück.

Wenn *filename* oder *Pfadnamen* ein **null** -Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen-1 zurück und legen **errno** auf **EINVAL**fest.

Weitere Informationen zu **errno** und Fehlercodes finden Sie unter [Errno-Konstanten](../../c-runtime-library/errno-constants.md).

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv**|**_searchenv**|**_searchenv**|**_wsearchenv**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_searchenv**|\<stdlib.h>|
|**_wsearchenv**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_searchenv.c
// compile with: /W3
// This program searches for a file in
// a directory that's specified by an environment variable.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";

   // Search for file in PATH environment variable:
   _searchenv( searchfile, envvar, pathbuffer ); // C4996
   // Note: _searchenv is deprecated; consider using _searchenv_s
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 8\VC\BIN\CL.EXE
```

## <a name="see-also"></a>Siehe auch

[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md)<br/>
