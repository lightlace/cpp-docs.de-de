---
title: _creat, _wcreat
ms.date: 11/04/2016
apiname:
- _creat
- _wcreat
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
ms.openlocfilehash: 901a95a6a9361f95f38749dacf1a5001d97b3761
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494990"
---
# <a name="creat-wcreat"></a>_creat, _wcreat

Erstellt eine neue Datei. **_creat** und **_wcreat** sind veraltet; verwenden Sie [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md) stattdessen.

## <a name="syntax"></a>Syntax

```C
int _creat(
   const char *filename,
   int pmode
);
int _wcreat(
   const wchar_t *filename,
   int pmode
);
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Name der neuen Datei.

*pmode*<br/>
Berechtigungseinstellung.

## <a name="return-value"></a>Rückgabewert

Diese Funktionen, sofern erfolgreich, geben einen Dateideskriptor an die erstellte Datei zurück. Andernfalls die Funktionen-1 zurück und legen Sie **Errno** wie in der folgenden Tabelle gezeigt.

|**Errno** Einstellung|Beschreibung|
|---------------------|-----------------|
|**EACCES**|*FileName* gibt eine vorhandene schreibgeschützte Datei oder ein Verzeichnis anstelle einer Datei.|
|**EMFILE**|Es sind keine Dateideskriptoren mehr verfügbar.|
|**ENOENT**|Die angegebene Datei wurde nicht gefunden.|

Wenn *Filename* ist **NULL**, rufen diese Funktionen den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** zu **EINVAL** und geben-1 zurück.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_creat** -Funktion erstellt eine neue Datei oder öffnet und verkleinert eine vorhandene. **_wcreat** ist eine Breitzeichen-Version von **_creat**; die *Filename* Argument **_wcreat** ist eine Breitzeichen-Zeichenfolge. **_wcreat** und **_creat** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

Wenn die Datei durch angegeben *Filename* ist nicht vorhanden, eine neue Datei mit der angegebenen berechtigungseinstellung erstellt und zum Schreiben geöffnet wird. Wenn die Datei bereits vorhanden ist und die berechtigungseinstellung das Schreiben ermöglicht, **_creat** schneidet die Datei, die Länge 0. der bisherige Inhalt und zum Schreiben geöffnet. Die berechtigungseinstellung *Pmode*, gilt nur für neu erstellte Dateien. Die neue Datei erhält die angegebene Berechtigungseinstellung, nachdem sie zum ersten Mal geschlossen wurde. Der ganzzahlige Ausdruck *Pmode* enthält eine oder beide der Manifestkonstanten **_S_IWRITE** und **_S_IREAD**, definiert in sys\stat. Wenn beide Konstanten gegeben sind, werden sie verknüpft, mit dem bitweisen or -Operator ( **&#124;** ). Die *Pmode* Parameter auf einen der folgenden Werte festgelegt ist.

|Wert|Definition|
|-----------|----------------|
|**_S_IWRITE**|Schreiben zugelassen.|
|**_S_IREAD**|Lesen erlaubt.|
|**_S_IREAD** &AMP;#124; **_S_IWRITE**|Lesen und Schreiben erlaubt.|

Wenn keine Schreibberechtigung gewährt wird, kann die Datei nur gelesen werden. Hinweis: Alle Dateien sind stets lesbar; es ist nicht möglich, nur Schreibberechtigungen zu vergeben. Die Modi **_S_IWRITE** und **_S_IREAD** | **_S_IWRITE** sind äquivalent. Mit geöffneten Dateien **_creat** werden immer im Kompatibilitätsmodus geöffnet (siehe [_sopen](sopen-wsopen.md)) mit **_SH_DENYNO**.

**_creat** wendet auf die aktuelle dateiberechtigungsmaske *Pmode* vor dem Festlegen der Berechtigungen (finden Sie unter [_umask](umask.md)). **_creat** wird in erster Linie für Kompatibilität mit früheren Bibliotheken bereitgestellt. Ein Aufruf von **_open** mit **_O_CREAT** und **_O_TRUNC** in die *Oflag* Parameter entspricht dem **_creat**und empfiehlt sich für neuen Code.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|
|**_wcreat**|\<io.h> oder \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_creat.c
// compile with: /W3
// This program uses _creat to create
// the file (or truncate the existing file)
// named data and open it for writing.

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int fh;

   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996
   // Note: _creat is deprecated; use _sopen_s instead
   if( fh == -1 )
      perror( "Couldn't create data file" );
   else
   {
      printf( "Created data file.\n" );
      _close( fh );
   }
}
```

```Output
Created data file.
```

## <a name="see-also"></a>Siehe auch

[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>
