---
title: remove, _wremove
ms.date: 11/04/2016
apiname:
- _wremove
- remove
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
- remove
- _wremove
- _tremove
helpviewer_keywords:
- tremove function
- _wremove function
- files [C++], deleting
- _tremove function
- files [C++], removing
- wremove function
- remove function
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
ms.openlocfilehash: d5636912ea36fd1b1412a556d516ac3e8184e0b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613968"
---
# <a name="remove-wremove"></a>remove, _wremove

Löschen einer Datei.

## <a name="syntax"></a>Syntax

```C
int remove(
   const char *path
);
int _wremove(
   const wchar_t *path
);
```

### <a name="parameters"></a>Parameter

*path*<br/>
Pfad der zu löschenden Datei.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt 0 zurück, wenn die Datei erfolgreich gelöscht wird. Andernfalls wird-1 zurückgegeben und legt **Errno** entweder auf **EACCES** , um anzugeben, dass der Pfad Gibt an, eine schreibgeschützte Datei oder die Datei geöffnet ist, oder **ENOENT** an, dass die Dateiname oder Pfad wurde nicht gefunden oder, dass der Pfad ein Verzeichnis angibt.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **remove**-Funktion löscht die von *path* angegebene Datei. **_wremove** ist eine Breitzeichen-Version von **entfe_rnen**; die *Pfad* Argument **_wremove** ist eine Breitzeichen-Zeichenfolge. **_wremove** und **entfe_rnen** Verhalten sich andernfalls identisch. Alle Handles zu einer Datei müssen geschlossen werden, bevor sie gelöscht werden kann.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tremove**|**remove**|**remove**|**_wremove**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**remove**|\<stdio.h> oder \<io.h>|
|**_wremove**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_remove.c
/* This program uses remove to delete crt_remove.txt */

#include <stdio.h>

int main( void )
{
   if( remove( "crt_remove.txt" ) == -1 )
      perror( "Could not delete 'CRT_REMOVE.TXT'" );
   else
      printf( "Deleted 'CRT_REMOVE.TXT'\n" );
}
```

### <a name="input-crtremovetxt"></a>Eingabe: crt_remove.txt

```Input
This file will be deleted.
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Deleted 'CRT_REMOVE.TXT'
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
