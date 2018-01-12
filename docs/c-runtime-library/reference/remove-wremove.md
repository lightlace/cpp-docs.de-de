---
title: remove, _wremove | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- tremove function
- _wremove function
- files [C++], deleting
- _tremove function
- files [C++], removing
- wremove function
- remove function
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 11050e3f168f390fa7a80aa6febf08a4be695c3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="remove-wremove"></a>remove, _wremove
Löschen einer Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int remove(  
   const char *path   
);  
int _wremove(  
   const wchar_t *path   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *path*  
 Pfad der zu löschenden Datei.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt 0 zurück, wenn die Datei erfolgreich gelöscht wird. Andernfalls wird –1 zurückgegeben und `errno` entweder auf `EACCES` festgelegt, um anzuzeigen, dass der Pfad eine schreibgeschützte Datei angibt oder die Datei geöffnet ist, oder auf **ENOENT** festgelegt, um zu zeigen, dass Dateiname oder Pfad nicht gefunden wurden oder der Pfad ein Verzeichnis angibt.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die **remove**-Funktion löscht die von *path* angegebene Datei. `_wremove` ist eine Breitzeichenversion von **_remove**. Das *path*-Argument für `_wremove` ist eine Breitzeichenfolge. `_wremove` und **_remove** verhalten sich andernfalls identisch. Alle Handles zu einer Datei müssen geschlossen werden, bevor sie gelöscht werden kann.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tremove`|**remove**|**remove**|`_wremove`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|**remove**|\<stdio.h> oder \<io.h>|  
|`_wremove`|\<stdio.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
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
  
## <a name="input-crtremovetxt"></a>Eingabe: crt_remove.txt  
  
```  
This file will be deleted.  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
Deleted 'CRT_REMOVE.TXT'  
```  
  
## <a name="see-also"></a>Siehe auch  
 [File Handling (Dateibehandlung)](../../c-runtime-library/file-handling.md)   
 [_unlink, _wunlink](../../c-runtime-library/reference/unlink-wunlink.md)