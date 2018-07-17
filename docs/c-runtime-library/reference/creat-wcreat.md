---
title: _creat _wcreat | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a6b987faa30439f0f374838fe7fcd4d942b8cc7
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
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

Diese Funktionen, sofern erfolgreich, geben einen Dateideskriptor an die erstellte Datei zurück. Andernfalls, die Funktionen – 1 zurück und legen Sie **Errno** wie in der folgenden Tabelle gezeigt.

|**Errno** Einstellung|Beschreibung|
|---------------------|-----------------|
|**EACCES**|*FileName* gibt eine vorhandene schreibgeschützte Datei oder ein Verzeichnis anstelle einer Datei.|
|**EMFILE**|Es sind keine Dateideskriptoren mehr verfügbar.|
|**ENOENT**|Die angegebene Datei wurde nicht gefunden.|

Wenn *Filename* ist **NULL**, rufen diese Funktionen den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL** und geben-1 zurück.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_creat** Funktion eine neue Datei erstellt oder öffnet und schneidet eine vorhandene ab. **_wcreat** ist eine Breitzeichen-Version von **_creat**; das *Filename* Argument **_wcreat** ist eine Breitzeichen-Zeichenfolge. **_wcreat** und **_creat** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

Wenn die Datei durch angegeben *Filename* nicht vorhanden ist, eine neue Datei wird erstellt, mit der angegebenen berechtigungseinstellung und zum Schreiben geöffnet wird. Wenn die Datei bereits vorhanden und kann Dateien geschrieben werden, werden seine berechtigungseinstellung **_creat** schneidet die Datei auf die Länge 0 (null) der vorherige Inhalt zerstört und zum Schreiben geöffnet. Die berechtigungseinstellung *Pmode*, betrifft nur die neu erstellte Dateien. Die neue Datei erhält die angegebene Berechtigungseinstellung, nachdem sie zum ersten Mal geschlossen wurde. Der Ganzzahlausdruck *Pmode* enthält eine oder beide der Manifestkonstanten **_S_IWRITE** und **_S_IREAD**, die in sys\stat definiert. Wenn beide Konstanten gegeben sind, werden sie verknüpft, mit einer bitweisen or -Operator ( **&#124;** ). Die *Pmode* Parameter auf einen der folgenden Werte festgelegt ist.

|Wert|Definition|
|-----------|----------------|
|**_S_IWRITE**|Schreiben zugelassen.|
|**_S_IREAD**|Lesen erlaubt.|
|**_S_IREAD** &AMP;#124; **_S_IWRITE**|Lesen und Schreiben erlaubt.|

Wenn keine Schreibberechtigung gewährt wird, kann die Datei nur gelesen werden. Hinweis: Alle Dateien sind stets lesbar; es ist nicht möglich, nur Schreibberechtigungen zu vergeben. Die Modi **_S_IWRITE** und **_S_IREAD** | **_S_IWRITE** sind äquivalent. Mit geöffneten Dateien **_creat** werden immer im Kompatibilitätsmodus geöffnet (siehe [_sopen](sopen-wsopen.md)) mit **_SH_DENYNO**.

**_creat** gilt die aktuelle dateiberechtigungsmaske auf *Pmode* vor dem Festlegen der Berechtigungen (siehe [_umask](umask.md)). **_creat** dient in erster Linie für die Kompatibilität mit früheren Bibliotheken. Ein Aufruf von **_open** mit **_O_CREAT** und **_O_TRUNC** in der *Oflag* Parameter entspricht **_creat**und ist für neuen Code vorzuziehen.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
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
