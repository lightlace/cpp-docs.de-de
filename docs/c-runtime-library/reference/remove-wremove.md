---
title: remove, _wremove | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- tremove function
- _wremove function
- files [C++], deleting
- _tremove function
- files [C++], removing
- wremove function
- remove function
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 97c258d79af8247af993732405d2c792a0822075
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

Jede dieser Funktionen gibt 0 zurück, wenn die Datei erfolgreich gelöscht wird. Hingegen gibt-1 zurück und legt sie fest **Errno** entweder **EACCES** um anzugeben, dass der Pfad eine schreibgeschützte Datei gibt oder die Datei geöffnet ist, oder auf **ENOENT** gibt an, dass die Dateiname oder Pfad nicht gefunden wurde oder, dass der Pfad ein Verzeichnis angegeben.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **remove**-Funktion löscht die von *path* angegebene Datei. **_wremove** ist eine Breitzeichen-Version von **ent_fernen**; das *Pfad* Argument **_wremove** ist eine Breitzeichen-Zeichenfolge. **_wremove** und **ent_fernen** Verhalten sich andernfalls identisch. Alle Handles zu einer Datei müssen geschlossen werden, bevor sie gelöscht werden kann.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tremove**|**remove**|**remove**|**_wremove**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
