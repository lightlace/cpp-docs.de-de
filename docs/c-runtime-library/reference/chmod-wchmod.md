---
title: _chmod, _wchmod | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _chmod
- _wchmod
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
- _chmod
- _wchmod
- wchmod
dev_langs:
- C++
helpviewer_keywords:
- _chmod function
- wchmod function
- file permissions [C++]
- chmod function
- files [C++], changing permissions
- _wchmod function
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: c0db1569ea6a90892b7eb3d0d8f08f3c9fcf7115
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="chmod-wchmod"></a>_chmod, _wchmod
Ändert die Dateiberechtigungseinstellungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _chmod(   
   const char *filename,  
   int pmode   
);  
int _wchmod(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Name der vorhandenen Datei.  
  
 `pmode`  
 Berechtigungseinstellung für die Datei.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Funktionen geben 0 zurück, wenn die Berechtigungseinstellung erfolgreich geändert wurde. Ein Rückgabewert "-1" gibt einen Fehler. Wenn die angegebene Datei nicht gefunden wurde, wird `errno` auf `ENOENT` gesetzt; wenn ein Parameter ungültig ist, wird `errno` auf `EINVAL` gesetzt.  
  
## <a name="remarks"></a>Hinweise  
 Die `_chmod` -Funktion ändert die Einstellung der vom angegebenen Datei `filename`. Die Berechtigungseinstellung steuert den Lese- und Schreibzugriff auf die Datei. Der ganzzahlige Ausdruck `pmode` enthält eine oder beide der folgenden Manifestkonstanten, die in SYS\Stat.h definiert sind.  
  
 `_S_IWRITE`  
 Schreiben erlaubt.  
  
 `_S_IREAD`  
 Lesen erlaubt.  
  
 `_S_IREAD | _S_IWRITE`  
 Lesen und Schreiben erlaubt.  
  
 Wenn beide Konstanten gegeben sind, werden sie mit dem bitweisen `OR`-Operator verbunden ( `|` ). Wenn keine Schreibberechtigung gewährt wird, kann die Datei nur gelesen werden. Hinweis: Alle Dateien sind stets lesbar; es ist nicht möglich, nur Schreibberechtigungen zu vergeben. Deshalb sind die Modi `_S_IWRITE` und `_S_IREAD | _S_IWRITE` gleichwertig.  
  
 `_wchmod` ist eine Breitzeichenversion von `_chmod`. Das `filename`-Argument für `_wchmod` ist eine Breitzeichenfolge. `_wchmod` und `_chmod` verhalten sich andernfalls identisch.  
  
 Diese Funktion überprüft ihre Parameter. Wenn `pmode` keine Kombination aus einer der Manifestkonstanten ist oder eine alternative Gruppe von Konstanten enthält, ignoriert die Funktion diese einfach. Wenn `filename` `NULL` ist, wird der Handler für ungültige Parameter wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt – 1 zurück.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tchmod`|`_chmod`|`_chmod`|`_wchmod`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_chmod`|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
|`_wchmod`|\<io.h> oder \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_chmod.c  
// This program uses _chmod to  
// change the mode of a file to read-only.  
// It then attempts to modify the file.  
//  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
// Change the mode and report error or success   
void set_mode_and_report(char * filename, int mask)  
{  
   // Check for failure   
   if( _chmod( filename, mask ) == -1 )  
   {  
      // Determine cause of failure and report.   
      switch (errno)  
      {  
         case EINVAL:  
            fprintf( stderr, "Invalid parameter to chmod.\n");  
            break;  
         case ENOENT:  
            fprintf( stderr, "File %s not found\n", filename );  
            break;  
         default:  
            // Should never be reached   
            fprintf( stderr, "Unexpected error in chmod.\n" );  
       }  
   }  
   else  
   {  
      if (mask == _S_IREAD)  
        printf( "Mode set to read-only\n" );  
      else if (mask & _S_IWRITE)  
        printf( "Mode set to read/write\n" );  
   }  
   fflush(stderr);  
}  
  
int main( void )  
{   
  
   // Create or append to a file.   
   system( "echo /* End of file */ >> crt_chmod.c_input" );  
  
   // Set file mode to read-only:   
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );  
  
   // Change back to read/write:   
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );   
}   
```  
  
```Output  
  
A line of text.  
  
```  
  
```Output  
  
      A line of text.Mode set to read-only  
Access is denied.  
Mode set to read/write  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat, _wstat-Funktionen](../../c-runtime-library/reference/stat-functions.md)
