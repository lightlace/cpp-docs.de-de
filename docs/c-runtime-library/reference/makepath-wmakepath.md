---
title: _makepath, _wmakepath
ms.date: 11/04/2016
apiname:
- _makepath
- _wmakepath
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
apitype: DLLExport
f1_keywords:
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
ms.openlocfilehash: 073f8aba6936aa33dafcef7ed47f5286802a4948
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285698"
---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath

Erstellen Sie einen Pfadnamen aus Komponenten. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="syntax"></a>Syntax

```C
void _makepath(
   char *path,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
void _wmakepath(
   wchar_t *path,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
```

### <a name="parameters"></a>Parameter

*path*<br/>
Vollständiger Pfadpuffer

*drive*<br/>
Enthält einen Buchstaben (A, B usw.) für das gewünschte Laufwerk und einen optionalen nachgestellten Doppelpunkt. **_makepath** fügt den Doppelpunkt automatisch in den zusammengesetzten Pfad, wenn sie nicht vorhanden ist. Wenn *Laufwerk* ist **NULL** oder auf eine leere Zeichenfolge verweist, erscheint kein Laufwerksbuchstabe in die zusammengesetzte *Pfad* Zeichenfolge.

*dir*<br/>
Enthält den Pfad der Verzeichnisse, ausgenommen die Laufwerkkennzeichner oder den tatsächlichen Dateinamen. Der nachstehende Schrägstrich ist optional, und einem Schrägstrich (/) oder einen umgekehrten Schrägstrich (\\) oder beide können verwendet werden, in einem einzelnen *Dir* Argument. Wenn kein nachstehender Schrägstrich (/ oder \\) angegeben ist, wird er automatisch eingefügt. Wenn *Dir* ist **NULL** oder verweist auf eine leere Zeichenfolge und kein Verzeichnispfad in die zusammengesetzte eingefügt wird *Pfad* Zeichenfolge.

*fname*<br/>
Enthält den Basisdateinamen ohne Dateinamenerweiterungen. Wenn *Fname* ist **NULL** oder verweist auf eine leere Zeichenfolge und kein Dateiname wird eingefügt, in die zusammengesetzte *Pfad* Zeichenfolge.

*ext*<br/>
Enthält die eigentliche Dateinamenerweiterung mit oder ohne führenden Punkt (.). **_makepath** fügt automatisch den Punkt, wenn es nicht, in angezeigt wird *Ext*. Wenn *Ext* ist **NULL** oder verweist auf eine leere Zeichenfolge, die keine Erweiterung eingefügt wird, in die zusammengesetzte *Pfad* Zeichenfolge.

## <a name="remarks"></a>Hinweise

Die **_makepath** Funktion erstellt eine zusammengesetzte Pfadzeichenfolge aus einzelnen Komponenten, die das Ergebnis in speichert *Pfad*. Die *Pfad* sind zum Beispiel einen Laufwerkbuchstaben, Pfad, Dateiname und Dateierweiterung. **_wmakepath** ist eine Breitzeichen-Version von **_makepath**; die Argumente für **_wmakepath** sind Breitzeichen Zeichenfolgen. **_wmakepath** und **_makepath** Verhalten sich andernfalls identisch.

**Sicherheitshinweis** Verwenden Sie eine mit NULL endende Zeichenfolge. Um Pufferüberläufe zu vermeiden, die Null-terminierte Zeichenfolge darf nicht übersteigen die Größe der *Pfad* Puffer. **_makepath** gewährleistet nicht, dass die Länge der Zeichenfolge für den zusammengesetzten Pfad nicht überschreitet **_MAX_PATH**. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

Die *Pfad* Argument muss auf einen leeren Puffer groß genug für den vollständigen Pfad verweisen. Die kombinierte *Pfad* darf nicht größer als sein die **_MAX_PATH** Konstante, die in Stdlib.h.

Wenn der Pfad ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Darüber hinaus **Errno** nastaven NA hodnotu **EINVAL**. **NULL** Werte für alle anderen Parameter zulässig sind.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_makepath.c
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];

   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996
   // Note: _makepath is deprecated; consider using _makepath_s instead
   printf( "Path created with _makepath: %s\n\n", path_buffer );
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996
   // Note: _splitpath is deprecated; consider using _splitpath_s instead
   printf( "Path extracted with _splitpath:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath: c:\sample\crt\makepath.c

Path extracted with _splitpath:
   Drive: c:
   Dir: \sample\crt\
   Filename: makepath
   Ext: .c
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>
