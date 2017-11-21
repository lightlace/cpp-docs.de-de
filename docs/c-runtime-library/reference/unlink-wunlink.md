---
title: _unlink, _wunlink | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _unlink
- _wunlink
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
- _tunlink
- _unlink
- wunlink
- _wunlink
dev_langs: C++
helpviewer_keywords:
- files [C++], deleting
- _wunlink function
- wunlink function
- unlink function
- _unlink function
- tunlink function
- files [C++], removing
- _tunlink function
ms.assetid: 5e4f5f1b-1e99-4391-9b18-9ac63c32fae8
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e98fb76faad72cedf48d8cc6baa7113870273d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="unlink-wunlink"></a>_unlink, _wunlink
Löschen einer Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _unlink(  
   const char *filename   
);  
int _wunlink(  
   const wchar_t *filename   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Name der zu entfernenden Datei.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt bei Erfolg 0 zurück. Anderenfalls gibt die Funktion-1 zurück und legt `errno` auf `EACCES`, was bedeutet, dass den Pfad Gibt eine schreibgeschützte Datei oder `ENOENT`, womit der Datei oder Pfad nicht gefunden wird oder der Pfad hat ein Verzeichnis angegeben.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_unlink`-Funktion löscht die von `filename` angegebene Datei. `_wunlink` ist eine Breitzeichenversion von `_unlink`. Das `filename`-Argument für `_wunlink` ist eine Breitzeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tunlink`|`_unlink`|`_unlink`|`_wunlink`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_unlink`|\<io.h> und \<stdio.h>|  
|`_wunlink`|\<io.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="code-example"></a>Codebeispiel  
 Dieses Programm verwendet _unlink, um CRT_UNLINK.TXT zu löschen.  
  
```  
// crt_unlink.c  
  
#include <stdio.h>  
  
int main( void )  
{  
   if( _unlink( "crt_unlink.txt" ) == -1 )  
      perror( "Could not delete 'CRT_UNLINK.TXT'" );  
   else  
      printf( "Deleted 'CRT_UNLINK.TXT'\n" );  
}  
```  
  
### <a name="input-crtunlinktxt"></a>Eingabe: crt_unlink.txt  
  
```  
This file will be deleted.  
```  
  
### <a name="sample-output"></a>Beispielausgabe  
  
```  
Deleted 'CRT_UNLINK.TXT'  
```  
  
## <a name="see-also"></a>Siehe auch  
 [File Handling (Dateibehandlung)](../../c-runtime-library/file-handling.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [remove, _wremove](../../c-runtime-library/reference/remove-wremove.md)