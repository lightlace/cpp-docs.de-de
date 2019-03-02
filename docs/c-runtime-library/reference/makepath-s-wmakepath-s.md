---
title: _makepath_s, _wmakepath_s
ms.date: 11/04/2016
apiname:
- _wmakepath_s
- _makepath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
ms.openlocfilehash: 3536569fd3e77a353003e1372d5dc4ee6e4ee3fb
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210652"
---
# <a name="makepaths-wmakepaths"></a>_makepath_s, _wmakepath_s

Erstellt einen Pfadnamen aus Komponenten Dies sind Versionen von [_makepath, _wmakepath](makepath-wmakepath.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t _makepath_s(
   char *path,
   size_t sizeInBytes,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
errno_t _wmakepath_s(
   wchar_t *path,
   size_t sizeInWords,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
template <size_t size>
errno_t _makepath_s(
   char (&path)[size],
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
); // C++ only
template <size_t size>
errno_t _wmakepath_s(
   wchar_t (&path)[size],
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
); // C++ only
```

### <a name="parameters"></a>Parameter

*path*<br/>
Vollständiger Pfadpuffer

*sizeInWords*<br/>
Größe des Puffers in Worten

*sizeInBytes*<br/>
Größe des Puffers in Byte.

*drive*<br/>
Enthält einen Buchstaben (A, B usw.) für das gewünschte Laufwerk und einen optionalen nachgestellten Doppelpunkt. **_makepath_s** fügt den Doppelpunkt automatisch in den zusammengesetzten Pfad, wenn sie nicht vorhanden ist. Wenn *Laufwerk* ist **NULL** oder auf eine leere Zeichenfolge verweist, erscheint kein Laufwerksbuchstabe in die zusammengesetzte *Pfad* Zeichenfolge.

*dir*<br/>
Enthält den Pfad der Verzeichnisse, ausgenommen die Laufwerkkennzeichner oder den tatsächlichen Dateinamen. Der nachstehende Schrägstrich ist optional, und einem Schrägstrich (/) oder einen umgekehrten Schrägstrich (\\) oder beide können verwendet werden, in einem einzelnen *Dir* Argument. Wenn kein nachstehender Schrägstrich (/ oder \\) angegeben ist, wird er automatisch eingefügt. Wenn *Dir* ist **NULL** oder verweist auf eine leere Zeichenfolge und kein Verzeichnispfad in die zusammengesetzte eingefügt wird *Pfad* Zeichenfolge.

*fname*<br/>
Enthält den Basisdateinamen ohne Dateinamenerweiterungen. Wenn *Fname* ist **NULL** oder verweist auf eine leere Zeichenfolge und kein Dateiname wird eingefügt, in die zusammengesetzte *Pfad* Zeichenfolge.

*ext*<br/>
Enthält die eigentliche Dateinamenerweiterung mit oder ohne führenden Punkt (.). **_makepath_s** fügt automatisch den Punkt, wenn es nicht, in angezeigt wird *Ext*. Wenn *Ext* ist **NULL** oder verweist auf eine leere Zeichenfolge, die keine Erweiterung eingefügt wird, in die zusammengesetzte *Pfad* Zeichenfolge.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.

### <a name="error-conditions"></a>Fehlerbedingungen

|*path*|*sizeInWords* / *sizeInBytes*|Zurück|Inhalt der *Pfad*|
|------------|------------------------------------|------------|------------------------|
|**NULL**|any|**EINVAL**|nicht geändert|
|any|<= 0|**EINVAL**|nicht geändert|

Wenn Fehlerzustände wie die oben genannten auftreten, wird ein Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktionen gibt **EINVAL**. **NULL** ist zulässig, für die Parameter *Laufwerk*, *Fname*, und *Ext*. Weitere Informationen zum Verhalten, wenn diese Parameter NULL-Zeiger oder leere Zeichenfolgen sind, finden Sie im Abschnitt „Hinweise“.

## <a name="remarks"></a>Hinweise

Die **_makepath_s** Funktion erstellt eine zusammengesetzte Pfadzeichenfolge aus einzelnen Komponenten, die das Ergebnis in speichert *Pfad*. Die *Pfad* sind zum Beispiel eine Laufwerkbuchstaben, Pfad, Dateiname und Dateierweiterung. **_wmakepath_s** ist eine Breitzeichen-Version von **_makepath_s**; die Argumente für **_wmakepath_s** sind Breitzeichen Zeichenfolgen. **_wmakepath_s** und **_makepath_s** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

Die *Pfad* Argument muss auf einen leeren Puffer groß genug für den vollständigen Pfad verweisen. Die kombinierte *Pfad* darf nicht größer als sein die **_MAX_PATH** Konstante, die in Stdlib.h.

Wenn der Pfad ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Darüber hinaus **Errno** nastaven NA hodnotu **EINVAL**. **NULL** Werte für alle anderen Parameter zulässig sind.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_makepath_s**|\<stdlib.h>|
|**_wmakepath_s**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_makepath_s.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];
   errno_t err;

   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",
                      "crt_makepath_s", "c" );
   if (err != 0)
   {
      printf("Error creating path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,
                       _MAX_FNAME, ext, _MAX_EXT );
   if (err != 0)
   {
      printf("Error splitting the path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path extracted with _splitpath_s:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c

Path extracted with _splitpath_s:
   Drive: c:
   Dir: \sample\crt\
   Filename: crt_makepath_s
   Ext: .c
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
