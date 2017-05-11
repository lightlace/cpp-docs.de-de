---
title: _getcwd, _wgetcwd | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wgetcwd
- _getcwd
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
dev_langs:
- C++
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ad70ffac5cbe6cc7c56dbad0930bc87b969a1857
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="getcwd-wgetcwd"></a>_getcwd, _wgetcwd
Ruft das aktuelle Arbeitsverzeichnis ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_getcwd(   
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetcwd(   
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 Speicherort für den Pfad.  
  
 `maxlen`  
 Maximale Länge des Pfads in Zeichen: `char` für `_getcwd` und `wchar_t` für `_wgetcwd`.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf `buffer`zurück. Ein `NULL` -Rückgabewert zeigt einen Fehler an, und `errno` wird entweder auf `ENOMEM`festgelegt, um anzugeben, dass nicht genügend Arbeitsspeicher zum Zuordnen von `maxlen` Bytes vorhanden ist (wenn ein `NULL` -Argument als `buffer`angegeben wird), oder auf `ERANGE`, um anzugeben, dass der Pfad länger als `maxlen` Zeichen ist. Wenn `maxlen` kleiner oder gleich Null ist, ruft diese Funktion einen Handler für ungültige Parameter auf, wie in [Parameter Validation](../../c-runtime-library/parameter-validation.md).  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_getcwd` -Funktion ruft für das Standardlaufwerk den vollständigen Pfad des aktuellen Arbeitsverzeichnis ab und speichert ihn unter `buffer`. Das ganzzahlige Argument `maxlen` gibt die maximale Länge für den Pfad an. Ein Fehler auftritt, wenn die Länge des Pfads (einschließlich das abschließende Nullzeichen) überschreitet `maxlen`. Das `buffer`-Argument kann `NULL` sein. Es wird dann automatisch ein Puffer mit einer Mindestgröße von `maxlen` (mehr nur bei Bedarf) zugeordnet und `malloc` zum Speichern des Pfades verwendet. Dieser Puffer kann später geleert werden, indem `free` aufgerufen und der `_getcwd` -Rückgabewert (ein Zeiger auf den zugeordneten Puffer) übergeben werden.  
  
 `_getcwd` gibt eine Zeichenfolge zurück, die den Pfad des aktuellen Arbeitsverzeichnisses repräsentiert. Wenn das aktuelle Arbeitsverzeichnis das Stammverzeichnis ist, endet die Zeichenfolge mit einem umgekehrten Schrägstrich ( `\` ). Wenn das aktuelle Arbeitsverzeichnis nicht das Stammverzeichnis ist, endet die Zeichenfolge mit dem Verzeichnisnamen und nicht mit einem umgekehrten Schrägstrich.  
  
 `_wgetcwd` ist eine Breitzeichenversion von `_getcwd`. Das Argument `buffer` und der Rückgabewert von `_wgetcwd` sind Zeichenfolgen mit Breitzeichen. `_wgetcwd` und `_getcwd` verhalten sich andernfalls identisch.  
  
 Wenn `_DEBUG` und `_CRTDBG_MAP_ALLOC` definiert sind, werden Aufrufe von `_getcwd` und `_wgetcwd` durch Aufrufe von `_getcwd_dbg` und `_wgetcwd_dbg` ersetzt, um das Debuggen von Speicherbelegungen zuzulassen. Weitere Informationen finden Sie unter [_getcwd_dbg, _wgetcwd_dbg](../../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetcwd`|`_getcwd`|`_getcwd`|`_wgetcwd`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_getcwd`|\<direct.h>|  
|`_wgetcwd`|\<direct.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_getcwd.c  
// This program places the name of the current directory in the   
// buffer array, then displays the name of the current directory   
// on the screen. Passing NULL as the buffer forces getcwd to allocate  
// memory for the path, which allows the code to support file paths  
// longer than _MAX_PATH, which are supported by NTFS.  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* buffer;  
  
   // Get the current working directory:   
   if( (buffer = _getcwd( NULL, 0 )) == NULL )  
      perror( "_getcwd error" );  
   else  
   {  
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );  
      free(buffer);  
   }  
}  
```  
  
```Output  
C:\Code  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)
