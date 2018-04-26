---
title: _searchenv_s, _wsearchenv_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wsearchenv_s
- _searchenv_s
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
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
dev_langs:
- C++
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
caps.latest.revision: 32
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a626ff2fbae86c7e1a1daf7f8fcdb2f5245c929d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s, _wsearchenv_s

Sucht mithilfe von Umgebungspfaden nach einer Datei. Diese Versionen von [_searchenv, _wsearchenv](searchenv-wsearchenv.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char *pathname,
   size_t numberOfElements
);
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname,
   size_t numberOfElements
);
template <size_t size>
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t (&pathname)[size]
); // C++ only
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Der Name der zu suchenden Datei.

*Variablenname*<br/>
Zu durchsuchende Umgebung.

*Pfadnamen*<br/>
Puffer zum Speichern des vollständigen Pfades.

*numberOfElements*<br/>
Größe der *Pathname* Puffer.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.

Wenn *Filename* ist eine leere Zeichenfolge ist der Rückgabewert **ENOENT**.

### <a name="error-conditions"></a>Fehlerbedingungen

|*filename*|*Variablenname*|*Pfadnamen*|*numberOfElements*|Rückgabewert|Inhalt der *Pfadnamen*|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|alle|alle|**NULL**|alle|**EINVAL**|n/v|
|**NULL**|alle|alle|alle|**EINVAL**|nicht geändert|
|alle|alle|alle|<= 0|**EINVAL**|nicht geändert|

Wenn eine dieser Fehlerbedingungen auftritt, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL** inventurüberprüfung **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_searchenv_s** -Routine sucht nach der Zieldatei, in der angegebenen Domäne. Die *Varname* Variable kann jede beliebige Umgebungsvariable oder benutzerdefinierte Variable, der angibt, wie z. B. eine Liste von Verzeichnispfaden, **Pfad**, **LIB**, und **EINSCHLIEßEN** . Da **_searchenv_s** wird Groß-/Kleinschreibung beachtet, *Varname* sollte die Groß-/Kleinschreibung der Umgebungsvariablen übereinstimmen. Wenn *Varname* entspricht nicht der Name einer Umgebungsvariablen in der Umgebung des Prozesses definiert, gibt die Funktion 0 (null) und die *Pathname* Variable bleibt unverändert.

Die Routine sucht zuerst im aktuellen Arbeitsverzeichnis nach der Datei. Wenn die Datei dort nicht gefunden wird, werden als Nächstes die in der Umgebungsvariablen angegebenen Verzeichnisse durchsucht. Wenn die Zieldatei in einem dieser Verzeichnisse ist, wird der neu erstellte Pfad in kopiert *Pathname*. Wenn die *Filename* Datei wurde nicht gefunden, *Pathname* enthält eine leere Null endende Zeichenfolge.

Die *Pathname* Puffer muss mindestens **_MAX_PATH** Zeichen lang sein, um die volle Länge des erstellten Pfadnamens zu unterstützen. Andernfalls **_searchenv_s** möglicherweise einem Überlauf der *Pathname* Puffer unerwarteten Verhalten führt.

**_wsearchenv_s** ist eine Breitzeichen-Version von **_searchenv_s**; die Argumente für **_wsearchenv_s** sind Zeichenfolgen mit Breitzeichen. **_wsearchenv_s** und **_searchenv_s** Verhalten sich andernfalls identisch.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv_s**|**_searchenv_s**|**_searchenv_s**|**_wsearchenv_s**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_searchenv_s**|\<stdlib.h>|
|**_wsearchenv_s**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_searchenv_s.c
/* This program searches for a file in
* a directory specified by an environment variable.
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";
   errno_t err;

   /* Search for file in PATH environment variable: */
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );
   if (err != 0)
   {
      printf("Error searching the path. Error code: %d\n", err);
   }
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE
```

## <a name="see-also"></a>Siehe auch

[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
