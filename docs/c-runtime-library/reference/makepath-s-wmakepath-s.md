---
title: _makepath_s, _wmakepath_s
ms.date: 11/04/2016
api_name:
- _wmakepath_s
- _makepath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 7efd7c8e5ce7314e6fe719073685377f4b325fbd
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952945"
---
# <a name="_makepath_s-_wmakepath_s"></a>_makepath_s, _wmakepath_s

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

*Antrie*<br/>
Enthält einen Buchstaben (A, B usw.) für das gewünschte Laufwerk und einen optionalen nachgestellten Doppelpunkt. **_makepath_s** fügt den Doppelpunkt automatisch in den zusammengesetzten Pfad ein, wenn dieser nicht vorhanden ist. Wenn das Laufwerk **null** ist oder auf eine leere Zeichenfolge verweist, wird kein Laufwerk Buchstabe in der Zeichenfolge für den zusammengesetzten *Pfad* angezeigt.

*dir*<br/>
Enthält den Pfad der Verzeichnisse, ausgenommen die Laufwerkkennzeichner oder den tatsächlichen Dateinamen. Der nachstehende Schrägstrich ist optional, und entweder ein Schrägstrich (/) oder ein umgekehrter Schrägstrich (\\) oder beides kann in einem einzelnen *dir* -Argument verwendet werden. Wenn kein nachstehender Schrägstrich (/ oder \\) angegeben ist, wird er automatisch eingefügt. Wenn *dir* **null** ist oder auf eine leere Zeichenfolge verweist, wird kein Verzeichnispfad in die zusammengesetzte *Pfad* Zeichenfolge eingefügt.

*fname*<br/>
Enthält den Basisdateinamen ohne Dateinamenerweiterungen. Wenn *fname* **null** ist oder auf eine leere Zeichenfolge verweist, wird kein Dateiname in die zusammengesetzte *Pfad* Zeichenfolge eingefügt.

*Antrags*<br/>
Enthält die eigentliche Dateinamenerweiterung mit oder ohne führenden Punkt (.). **_makepath_s** fügt den Zeitraum automatisch ein, wenn er nicht in *ext*angezeigt wird. Wenn *ext* **null** ist oder auf eine leere Zeichenfolge zeigt, wird keine Erweiterung in die zusammengesetzte *Pfad* Zeichenfolge eingefügt.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.

### <a name="error-conditions"></a>Fehlerbedingungen

|*path*|*sizeInWords* / *sizeInBytes*|Zurück|Inhalt des *Pfads*|
|------------|------------------------------------|------------|------------------------|
|**NULL**|any|**EINVAL**|nicht geändert|
|any|<= 0|**EINVAL**|nicht geändert|

Wenn Fehlerzustände wie die oben genannten auftreten, wird ein Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird **errno** auf **EINVAL** festgelegt, und die Funktionen gibt **EINVAL**zurück. **Null** ist für die Parameter " *Drive*", " *Name*" und " *ext*" zulässig. Weitere Informationen zum Verhalten, wenn diese Parameter NULL-Zeiger oder leere Zeichenfolgen sind, finden Sie im Abschnitt „Hinweise“.

## <a name="remarks"></a>Hinweise

Die **_makepath_s** -Funktion erstellt eine zusammengesetzte Pfad Zeichenfolge aus einzelnen Komponenten und speichert das Ergebnis im *Pfad*. Der *Pfad* kann einen Laufwerk Buchstaben, einen Verzeichnispfad, einen Dateinamen und eine Dateinamenerweiterung enthalten. **_wmakepath_s** ist eine breit Zeichen Version von **_makepath_s**. die Argumente für **_wmakepath_s** sind Zeichen folgen mit breit Zeichen. **_wmakepath_s** und **_makepath_s** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

Das *path* -Argument muss auf einen leeren Puffer zeigen, der groß genug ist, um den gesamten Pfad zu speichern. Der zusammengesetzte *Pfad* darf nicht größer als die **_MAX_PATH** -Konstante sein, die in "STDLIB. h" definiert ist.

Wenn path **null**ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Außerdem wird **errno** auf **EINVAL**festgelegt. **Null** -Werte sind für alle anderen Parameter zulässig.

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
